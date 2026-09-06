# GenieX

**Slug:** `genie-x` · **Kind:** runtime (executes code)

## What it is

wraps llama.cpp + GGML Hexagon backend + CLI

**Target hardware:** Hexagon NPU / CPU / GPU / hybrid

## Notes

The practical NPU path for GGUF. `geniex-bench --plugin {llama_cpp|qairt} --device {cpu|gpu|npu|hybrid|auto} -m <path-or-id>`. Confirmed working at ~/tools/geniex-bench (native Android/bionic, no proot).

## Do not confuse with

An *engine* — an engine wraps this plus a model plus a scheduler. This is the
layer that actually executes.
