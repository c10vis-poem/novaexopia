# llama.cpp

**Slug:** `llama-cpp` · **Kind:** runtime (executes code)

## What it is

base + GGML Hexagon backend

**Target hardware:** CPU / NPU via backend

## Notes

Includes the haozixu/llama.cpp-npu fork for Hexagon offload.

## Do not confuse with

An *engine* — an engine wraps this plus a model plus a scheduler. This is the
layer that actually executes.
