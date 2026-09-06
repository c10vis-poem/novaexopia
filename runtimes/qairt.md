# Qualcomm AI Runtime

**Slug:** `qairt` · **Kind:** runtime (executes code)

## What it is

libQnnHtp.so + genie-t2t-run CLI

**Target hardware:** Hexagon NPU (v79 on Alpha)

## Notes

Executes QNN graphs on the NPU directly. Needs LD_LIBRARY_PATH covering lib, lib/llama_cpp, lib/qairt, lib/qairt/htp-files — ALL FOUR, not just one. This was non-obvious and cost time.

## Do not confuse with

An *engine* — an engine wraps this plus a model plus a scheduler. This is the
layer that actually executes.
