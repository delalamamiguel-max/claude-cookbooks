# Claude Cookbooks

The Claude Cookbooks provide code and guides designed to help developers build with Claude, offering copy-able code snippets that you can easily integrate into your own projects.

## Prerequisites

To make the most of the examples in this cookbook, you'll need a Claude API key (sign up for free [here](https://www.anthropic.com)).

While the code examples are primarily written in Python, the concepts can be adapted to any programming language that supports interaction with the Claude API.

If you're new to working with the Claude API, we recommend starting with our [Claude API Fundamentals course](https://github.com/anthropics/courses/tree/master/anthropic_api_fundamentals) to get a solid foundation.

## Explore Further

Looking for more resources to enhance your experience with Claude and AI assistants? Check out these helpful links:

- [Anthropic developer documentation](https://docs.claude.com/claude/docs/guide-to-anthropics-prompt-engineering-resources)
- [Anthropic support docs](https://support.anthropic.com)
- [Anthropic Discord community](https://www.anthropic.com/discord)

## Contributing

The Claude Cookbooks thrives on the contributions of the developer community. We value your input, whether it's submitting an idea, fixing a typo, adding a new guide, or improving an existing one. By contributing, you help make this resource even more valuable for everyone.

To avoid duplication of efforts, please review the existing issues and pull requests before contributing.

If you have ideas for new examples or guides, share them on the [issues page](https://github.com/anthropics/anthropic-cookbook/issues).

## Table of recipes

### Capabilities
- [Classification](https://github.com/anthropics/anthropic-cookbook/tree/main/capabilities/classification): Explore techniques for text and data classification using Claude.
- [Retrieval Augmented Generation](https://github.com/anthropics/anthropic-cookbook/tree/main/capabilities/retrieval_augmented_generation): Learn how to enhance Claude's responses with external knowledge.
- [Summarization](https://github.com/anthropics/anthropic-cookbook/tree/main/capabilities/summarization): Discover techniques for effective text summarization with Claude.

### Tool Use and Integration
- [Tool use](https://github.com/anthropics/anthropic-cookbook/tree/main/tool_use): Learn how to integrate Claude with external tools and functions to extend its capabilities.
  - [Customer service agent](https://github.com/anthropics/anthropic-cookbook/blob/main/tool_use/customer_service_agent.ipynb)
  - [Calculator integration](https://github.com/anthropics/anthropic-cookbook/blob/main/tool_use/calculator_tool.ipynb)
  - [SQL queries](https://github.com/anthropics/anthropic-cookbook/blob/main/misc/how_to_make_sql_queries.ipynb)

### Third-Party Integrations
- [Retrieval augmented generation](https://github.com/anthropics/anthropic-cookbook/tree/main/third_party): Supplement Claude's knowledge with external data sources.
  - [Vector databases (Pinecone)](https://github.com/anthropics/anthropic-cookbook/blob/main/third_party/Pinecone/rag_using_pinecone.ipynb)
  - [Wikipedia](https://github.com/anthropics/anthropic-cookbook/blob/main/third_party/Wikipedia/wikipedia-search-cookbook.ipynb/)
  - [Web pages](https://github.com/anthropics/anthropic-cookbook/blob/main/misc/read_web_pages_with_haiku.ipynb)
- [Embeddings with Voyage AI](https://github.com/anthropics/anthropic-cookbook/blob/main/third_party/VoyageAI/how_to_create_embeddings.md)

### Multimodal Capabilities
- [Vision with Claude](https://github.com/anthropics/anthropic-cookbook/tree/main/multimodal): 
  - [Getting started with images](https://github.com/anthropics/anthropic-cookbook/blob/main/multimodal/getting_started_with_vision.ipynb)
  - [Best practices for vision](https://github.com/anthropics/anthropic-cookbook/blob/main/multimodal/best_practices_for_vision.ipynb)
  - [Interpreting charts and graphs](https://github.com/anthropics/anthropic-cookbook/blob/main/multimodal/reading_charts_graphs_powerpoints.ipynb)
  - [Extracting content from forms](https://github.com/anthropics/anthropic-cookbook/blob/main/multimodal/how_to_transcribe_text.ipynb)
- [Generate images with Claude](https://github.com/anthropics/anthropic-cookbook/blob/main/misc/illustrated_responses.ipynb): Use Claude with Stable Diffusion for image generation.

### Advanced Techniques
- [Sub-agents](https://github.com/anthropics/anthropic-cookbook/blob/main/multimodal/using_sub_agents.ipynb): Learn how to use Haiku as a sub-agent in combination with Opus.
- [Upload PDFs to Claude](https://github.com/anthropics/anthropic-cookbook/blob/main/misc/pdf_upload_summarization.ipynb): Parse and pass PDFs as text to Claude.
- [Automated evaluations](https://github.com/anthropics/anthropic-cookbook/blob/main/misc/building_evals.ipynb): Use Claude to automate the prompt evaluation process.
- [Enable JSON mode](https://github.com/anthropics/anthropic-cookbook/blob/main/misc/how_to_enable_json_mode.ipynb): Ensure consistent JSON output from Claude.
- [Create a moderation filter](https://github.com/anthropics/anthropic-cookbook/blob/main/misc/building_moderation_filter.ipynb): Use Claude to create a content moderation filter for your application.
- [Prompt caching](https://github.com/anthropics/anthropic-cookbook/blob/main/misc/prompt_caching.ipynb): Learn techniques for efficient prompt caching with Claude.

## Additional Resources

- [Anthropic on AWS](https://github.com/aws-samples/anthropic-on-aws): Explore examples and solutions for using Claude on AWS infrastructure.
- [AWS Samples](https://github.com/aws-samples/): A collection of code samples from AWS which can be adapted for use with Claude. Note that some samples may require modification to work optimally with Claude.


---

# Owned checkout guide

## Purpose and status

This owned reference fork preserves Anthropic’s recipes, links and MIT attribution. It is a collection of notebooks and examples, not one deployed application or a guarantee that every recipe runs with current provider APIs. Existing example outputs are demonstration material, not results produced by this review.

## Repository map

[`capabilities/`](capabilities/), [`tool_use/`](tool_use/), [`multimodal/`](multimodal/), [`third_party/`](third_party/) and other topical folders hold recipes. [`registry.yaml`](registry.yaml) and [`authors.yaml`](authors.yaml) index recipes and authors. [`scripts/`](scripts/) and [`tests/`](tests/) support validation; [`claude_agent_sdk/`](claude_agent_sdk/) and [`managed_agents/`](managed_agents/) have separate Python manifests. [`CLAUDE.md`](CLAUDE.md), [`.claude/`](.claude/) and [`CONTRIBUTING.md`](CONTRIBUTING.md) describe authoring/review workflows.

## Architecture and integrations

Examples call Claude and, where selected, external providers, tools, retrieval systems or agent services. The root Python package is a build-system placeholder; recipe behavior resides in notebooks and example code. There is no universal application architecture, persistence model or deployment environment shared by all recipes.

## Setup and environments

The root [manifest](pyproject.toml) requires Python >=3.11,<3.13 and uses uv with a lockfile. Nested projects may have different requirements. Upstream setup uses a private .env with ANTHROPIC_API_KEY; other recipes need their own provider configuration. Inspect only the recipe you intend to run and confirm model/API availability separately. No dependency installation, account setup or model verification was performed here.

## Safe commands

For this documentation review, use only local inspection such as `git status --short`, `git ls-files`, `git diff -- README.md` and `git diff --check`. Read referenced scripts as text; do not install dependencies, execute examples, authenticate, run tests or publish. `make install` synchronizes dependencies; `make fix` and format targets modify files. uv-run validation may resolve dependencies. Notebook execution can make paid API calls, write outputs and operate external resources.

## Testing and validation

The [Makefile](Makefile) distinguishes notebook structure checks from execution via `--execute-notebooks`; it also defines Ruff and pytest targets. None were run under the README-only constraint, including the checks normally requested by contributor guidance. Only static README structure, new relative targets, whitespace and original-byte preservation were checked. No recipe execution or provider success is claimed.

## Deployment and rollback

This repository distributes examples rather than a single owner deployment. Inspect a selected recipe’s infrastructure, assets and provider lifecycle before a future rollout. Reverting source does not delete external resources, undo tool actions or reverse API charges. No package, notebook, agent or service was published or started.

## Risks and guardrails

Preserve [MIT licensing](LICENSE), recipe attribution and existing notebook outputs. Keep keys, private prompts and newly generated sensitive outputs out of Git. Stored notebook outputs can contain input/output data; do not blindly rerun and commit them. Model names and provider behavior in existing examples are snapshot details whose present validity is unverified.

## Related documentation

Consult [CLAUDE.md](CLAUDE.md), [contributing guidance](CONTRIBUTING.md), [manifest](pyproject.toml), [Makefile](Makefile), [registry](registry.yaml), [authors](authors.yaml) and the selected recipe’s own documentation.
