# helix-llm-completions

Templates for simple language model completions in the helix editor. These are generally
based on [simonw/llm](https://github.com/simonw/llm), which provides a simple command
line interface for the ollama and llama.cpp backends. This repository provides
[model templates](https://llm.datasette.io/en/stable/templates.html#templates), helix
keymaps, and a quickstart shell script to get started.

```bash
# Install simonw/llm and a few tools
brew install llm
brew install ollama && llm install llm-ollama
llm install llm-tools-simpleeval llm-templates-github

# brew install llama.cpp && llm install llm-gguf

# Choose any LLM that fits in memory and supports tool calling
ollama pull hf.co/unsloth/Qwen3-4B-Instruct-2507-GGUF:Q4_K_M

# [Optional] Set the newly downloaded model as the default
llm models default "hf.co/unsloth/Qwen3-4B-Instruct-2507-GGUF:Q4_K_M"
```

To use these templates from the command line, enter the following:

```bash
llm --template gh:janbridley/helix-llm-completions/feature "Write a hello world script in c"
```

To use the template inside helix:

```toml
# Add this to your config.toml to run our LLM completion with space-space-p
# NOTE: this pulls in the entire file as a buffer, so it may be slow for compute-limited
#       devices. Removing '-f %{buffer_name}' will dramatically speed up processing
[keys.normal.space.space]
p = [
  """:insert-output llm --template gh:janbridley/helix-llm-completions/feature \
     '%{selection}' -f %{buffer_name} --no-stream""",
]
```
