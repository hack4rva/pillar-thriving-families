
# Research Output Directory

This directory contains the outputs of research prompts run via the Perplexity runner or manually.

## Structure

Each file in this directory corresponds to a prompt in `05_prompts/research/` and represents the research output for that prompt.

## How to populate

1. Run prompts via the Perplexity runner (utilizing the [Perplexity Python API](https://github.com/perplexityai/perplexity-py)): 
 ```bash
 python 05_prompts/perplexity_runner/run_all.py 05_prompts/research
 ```
2. Outputs are saved as `<prompt_basename>.md` and `<prompt_basename>.json`
3. Review outputs and log confirmed sources in `evidence_log.md`

## Index

The `index.json` file in this directory provides a summary of all available research documents for use by the `research_search` skill (conceptually similar to [Azure AI Search skillsets](https://learn.microsoft.com/en-us/azure/search/tutorial-skillset)).

## Status

This directory is empty until research prompts are run. Run `scripts/run_all_deep_research.py` (based on architectures like [LangChain's open_deep_research](https://github.com/langchain-ai/open_deep_research)) or use the Perplexity runner to populate it.