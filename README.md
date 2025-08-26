# helix-llm-completions
Templates for simple language model completions in the helix editor. These are generally based on [simonw/llm](https://github.com/simonw/llm), which provides a simple command line interface for the ollama and llama.cpp backends. This repository provides [model templates](https://llm.datasette.io/en/stable/templates.html#templates), helix keymaps, and a quickstart shell script to get started.

```bash
brew install llm
llm install llm-tools-simpleeval llm-templates-github
brew install ollama && llm install llm-ollama
brew install llama.cpp && llm install llm-gguf

# Choose any LLM that fits in memory and supports tool calling
ollama pull hf.co/unsloth/Qwen3-4B-Instruct-2507-GGUF:Q4_K_M


```
