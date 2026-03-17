# GRTC GTFS, Fast: From Open Feeds to "Nearest Bus Stop" in 48 Hours

## Executive Summary
For a 48-hour hackathon focused on connecting youth employment programs with transit access, the Greater Richmond Transit Company (GRTC) provides accessible static GTFS data, though navigating the sources requires care. Reliable access via state aggregators and a Pythonic geospatial stack (Pandas, GeoPandas, Partridge) allows a team to produce "nearest bus stop" insights rapidly. The primary risks involve data freshness and coordinate reference system (CRS) pitfalls during spatial joins. By focusing on a static-first approach and leveraging pre-built Python libraries, a team can deliver a functional, enriched program directory within a 10 to 14-hour development window.

## Where to Get GRTC GTFS
Accessing GRTC GTFS data involves choosing between state-level open data portals and transit feed aggregators. Use the DRPT Clearinghouse or Transitland for up-to-date full feeds, and treat the Virginia Open Data per-file extracts as reference backups.

### Virginia Open Data Portal
The Virginia Open Data Portal hosts individual GTFS component files for GRTC, including Stops, Routes, Trips, and Shapes [1] [2] [3] [4]. These files show a publication date of December 10, 2024, with an "Ad Hoc" update cadence [1] [2]. Notably, the Trips dataset contains multiple historical resources (e.g., Jan 2024, Jun 2024, Oct 2024) [4], and some files are labeled for "Datathon 2025" [1] [2], suggesting they may be convenience extracts rather than canonical, rolling operations data.

### Transitland Aggregator
Transitland provides a comprehensive historical view, showing 22 versions of the GRTC feed under the Onestop ID `f-grtc~va` [5]. This is highly useful for version selection and obtaining a complete, bundled ZIP file of the static feed.

### DRPT GTFS Feed Clearinghouse
The Virginia Department of Rail and Public Transportation (DRPT) maintains a GTFS Feed Clearinghouse that supports and aggregates feeds for many transit agencies in Virginia [6]. This should be the primary target for confirming the most current, official GRTC link on Day 1 of the hackathon.

### GRTC Real-Time Data
While GRTC's official website advertises a consumer-facing "Bus Tracker" with real-time GPS location data and predictive arrival times [7] [8], there is no publicly documented developer API or GTFS-realtime endpoint readily available. Teams should exclude real-time features from the MVP unless a specific URL is obtained.

| Source | Access Method | Format | Freshness / Cadence | Pros & Cons |
| :--- | :--- | :--- | :--- | :--- |
| **DRPT Clearinghouse** | Direct Download | Full ZIP | Maintained by State | **Pro:** Canonical state source. **Con:** Requires manual verification of GRTC update frequency. |
| **Transitland** | Web / API | Full ZIP | 22 historical versions | **Pro:** Easy version control and bundled feeds. **Con:** May lag slightly behind direct agency releases. |
| **VA Open Data Portal** | Web Download | Per-file CSV/TXT | Ad Hoc (Pub: Dec 2024) | **Pro:** Easy to inspect individual files. **Con:** Fragmented; risk of mismatched versions across files. |

*Takeaway: Prioritize Transitland or DRPT for a unified ZIP file to ensure relational integrity between routes, trips, and stops.*

## GTFS Schema Essentials
A standard GTFS feed is a collection of CSV files zipped together. For the "nearest bus stop" MVP, only a subset of these files is required.

### Mandatory for MVP Proximity
To calculate the nearest stop, you only strictly need the `stops.txt` file [2]. This file contains the `stop_id`, `stop_name`, `stop_lat`, and `stop_lon` [2]. This provides the geographic coordinates necessary to measure distance from the youth program locations.

### Useful Enrichment
To make the nearest stop actionable, users need to know *which* buses serve that stop. This requires joining three additional files:
* `routes.txt`: Contains `route_id`, `route_short_name`, `route_long_name`, and `route_color` [3].
* `trips.txt`: Links a `route_id` to a specific journey (`trip_id`) and includes `service_id` and `direction_id` [4].
* `stop_times.txt`: Links a `trip_id` to a `stop_id`, providing the sequence of stops and arrival/departure times.

### Operational Context (Nice-to-Have)
If time permits, `calendar.txt` and `calendar_dates.txt` can be used to filter services by day of the week (e.g., identifying weekday vs. weekend routes). The `shapes.txt` file provides geospatial paths for mapping routes [1], but is optional and not required for proximity calculations.

## Hackathon Tooling
A minimal, proven Python stack is ideal for a 48-hour sprint. You do not need to stand up a database to process GTFS data for a city the size of Richmond.

### Libraries and Installation
The core stack relies on Pandas and GeoPandas. For GTFS-specific parsing, `partridge` is highly recommended. It is a fast, forgiving Python GTFS reader built on Pandas DataFrames [9] [10]. Alternatively, `gtfs-kit` is a Python 3.10+ library for analyzing GTFS data in memory [11].
```bash
pip install partridge geopandas scikit-learn shapely
```

### Reading GTFS Fast
Partridge loads only what you need into memory and builds a dependency graph rooted at `trips.txt` [10]. This allows you to easily filter the feed to specific dates or routes without writing complex SQL joins.

### Computing Nearest Reliably
To find the nearest stop, use GeoPandas' `sjoin_nearest` function, which performs a spatial join based on the distance between geometries [12]. Alternatively, for pure coordinate math without projecting, `scikit-learn`'s `BallTree` can be used with the Haversine distance metric, provided coordinates are converted to radians [13].

## Implementation Guide
Follow these practical steps to overlay program addresses with GRTC stops.

### Step 0: Confirm and Download Feed
Download the latest GRTC GTFS ZIP from the DRPT Clearinghouse or Transitland. Avoid downloading individual files from the VA Open Data portal unless necessary, to prevent version mismatches.

### Step 1: Validate and Currency Check
Check the `feed_info.txt` file (if present) to ensure the feed is currently active. If absent, check the maximum dates in `calendar.txt`.

### Step 2: Prepare and Geocode Program Addresses
Batch geocode the youth employment program addresses using a free service like the Census Geocoder or Nominatim. Store the resulting latitude and longitude, along with a confidence score. Budget time for manual review of low-confidence matches.

### Step 3: Load GTFS Stops and Standardize CRS
Use Partridge to load `stops.txt` into a Pandas DataFrame, then convert it to a GeoDataFrame. **Critical:** GeoPandas warns that `sjoin_nearest` results will be inaccurate if geometries are in a geographic CRS (like WGS84/EPSG:4326) [12]. Project both the stops and the program locations to a local metric CRS (e.g., EPSG:32618 for UTM Zone 18N) before calculating distances.

### Step 4: Nearest-Stop Join
Execute `geopandas.sjoin_nearest(programs_gdf, stops_gdf, distance_col="distance_m")` [12]. This will append the nearest `stop_id` and the distance in meters to each program record.

### Step 5: Route and Service Context
Join the resulting `stop_id`s against `stop_times`, `trips`, and `routes` to aggregate a list of `route_short_name`s that service each identified stop.

### Step 6: Export and Integrate
Export the final dataset to CSV or JSON for integration into the program directory.

| Output Field | Source | Description |
| :--- | :--- | :--- |
| `program_id` | User Data | Unique identifier for the youth program. |
| `nearest_stop_id` | GTFS `stops.txt` | The ID of the closest GRTC bus stop. |
| `stop_name` | GTFS `stops.txt` | Human-readable name of the stop. |
| `distance_m` | GeoPandas | Straight-line distance in meters. |
| `distance_min` | Calculated | Estimated walking time (distance_m / 80 meters per min). |
| `routes_available` | GTFS `routes.txt` | Array of route names servicing the stop. |

*Takeaway: This schema provides both the geographic proximity and the practical transit context needed by end-users.*

## Time & Resourcing Plan
For a team with basic Python/Pandas skills, expect this analysis to take 10 to 14 engineer-hours, fitting comfortably within a 48-hour hackathon.

### Day 1: Data Prep (5-7 hours)
* **0.5h:** Source confirmation and download.
* **0.5h:** Environment setup (`pip install`).
* **1.0h:** Feed ingestion and validation using Partridge.
* **2.0-3.0h:** Address cleaning and batch geocoding (this is often the longest bottleneck).
* **1.0-2.0h:** Prototype the proximity join using GeoPandas.

### Day 2: Enrichment and Handoff (5-7 hours)
* **1.0-2.0h:** Finish geocoding QA and manual fix-ups.
* **2.0-3.0h:** Finalize the nearest-stop logic and write the joins to attach route names.
* **1.0h:** Export the final schema and document the pipeline.
* **1.0-2.0h:** Stretch goals (e.g., mapping).

## Data Quality & Risk Management
Several risks can derail a hackathon timeline if not anticipated.

### Freshness and Versioning
Transit schedules change. Always verify the feed's valid dates. Using the VA Open Data portal's "Datathon" files [1] may result in building against outdated 2024 schedules.

### CRS and Distance Accuracy
Failing to project coordinates out of EPSG:4326 before running `sjoin_nearest` will result in distances measured in degrees, which are useless for walking estimates [12]. Always project to a metric CRS.

### Geocoding Accuracy
Free geocoders will fail on poorly formatted addresses. Implement a confidence threshold and manually review any program address that fails to geocode accurately.

## Optional Enhancements in 48 Hours
If the team finishes early, consider these high-value additions:
* **Walking Time:** Convert the distance in meters to an estimated walking time (assuming ~80 meters per minute).
* **Frequency Bins:** Use `stop_times.txt` to count the number of departures between 8 AM and 10 AM to label a stop as "High Frequency" or "Low Frequency".
* **Visual Map:** Export the joined data as GeoJSON and throw it into a basic Leaflet map or QGIS for the final presentation.

## Inferences
* We infer that a current, bundled GTFS ZIP is accessible via DRPT or Transitland, as the VA Open Data per-file extracts (labeled "Datathon") may not represent the latest production schedule.
* We infer that no public GRTC GTFS-realtime endpoints are available for unauthenticated developer use, based on the lack of documentation on the GRTC site.
* We assume the list of youth programs is small enough (a few hundred) that free batch geocoding is feasible without hitting severe rate limits.

## Unknowns
* The exact URL and version date of the absolute latest official GRTC static GTFS ZIP (whether DRPT is perfectly synced with GRTC's internal systems).
* Whether GRTC exposes GTFS-realtime feeds (Trip Updates, Vehicle Positions) privately upon request.
* The initial quality and formatting of the youth program address list, which heavily dictates the geocoding time budget.

## References

1. *Shapes  GRTC GTFS - Dataset - Virginia Open Data Portal*. https://data.virginia.gov/dataset/shapes-grtc-gtfs
2. *Stops  GRTC GTFS - Dataset - Virginia Open Data Portal*. https://data.virginia.gov/dataset/stops-grtc-gtfs
3. *Routes  GRTC GTFS - Dataset - Virginia Open Data Portal*. https://data.virginia.gov/dataset/routes-grtc-gtfs
4. *Trips  GRTC GTFS - Dataset - Virginia Open Data Portal*. https://data.virginia.gov/dataset/trips-grtc-gtfs
5. *GTFS feed: Greater Richmond Transit Company (GRTC)*. https://www.transit.land/feeds/f-grtc~va
6. *GTFS Feed Clearinghouse - DRPT*. https://drpt.virginia.gov/data/gtfs-feed-clearinghouse/
7. *Bus Tracking -GRTC*. https://www.ridegrtc.com/maps-and-schedules/bus-tracking/
8. *GRTC: Home*. https://www.ridegrtc.com/
9. *Producing Data - General Transit Feed Specification*. https://gtfs.org/resources/producing-data/
10. *Partridge — partridge 1.1.1 documentation*. https://partridge.readthedocs.io/en/stable/readme.html
11. *GitHub - araichev/gtfs_kit: A Python library for analyzing GTFS feeds. · GitHub*. https://github.com/araichev/gtfs_kit
12. *geopandas.sjoin_nearest — GeoPandas 1.1.2.dev77+g16040f07c.d20260308 documentation*. https://geopandas.org/en/latest/docs/reference/api/geopandas.sjoin_nearest.html
13. *Using Scikit-learn's Binary Trees to Efficiently Find Latitude and Longitude Neighbors | Towards Data Science*. https://towardsdatascience.com/using-scikit-learns-binary-trees-to-efficiently-find-latitude-and-longitude-neighbors-909979bd929b/