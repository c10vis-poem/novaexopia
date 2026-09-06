# ONNX Runtime

**Slug:** `onnx-runtime` · **Kind:** runtime (executes code)

## What it is

ORT + QNN Execution Provider

**Target hardware:** NPU via QNN EP

## Notes

The ONNX path to the NPU. Alternative to GGUF/QAIRT.

## Do not confuse with

An *engine* — an engine wraps this plus a model plus a scheduler. This is the
layer that actually executes.
