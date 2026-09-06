# NovÆxopia

**Tools, harness, engine — the claw.** Runtimes, engines, weight configs, the
model roster.

## What lives here vs elsewhere

| This repo | Elsewhere |
|---|---|
| **What** an agent runs on — runtimes, engines, weights | **Who** the agent is → `novus-aexenti` |
| Model roster + RAM math + node targeting | Protocols → `aesop-xi` |
| Engine configs, serving surfaces | The corpus → `novae-xorpus` |

## Terminology — these are not interchangeable

| Term | Means |
|---|---|
| **SDK** | Compile-time tools. Headers, libs, toolchain. **Does not execute your model.** |
| **Runtime** | Executes code. `libQnnHtp.so`, llama.cpp, ONNX Runtime, CUDA. |
| **Engine** | Wrapper around runtime + model + scheduler. The serving surface. |
| **Model** | Trained weights. A file. Does nothing by itself. |

Every time one of these gets used for another, that's a bug. Full glossary:
`novae-xorpus/canon/DECISIONS-LOCKED.md`.

## Layout

```
runtimes/     what executes code
engines/      runtime + model + scheduler wrappers
weights/      active / candidates / rejected / voice / vision — the model roster
config/       profile YAMLs, concurrency policy
manifest.jsonl
```

## The executor/query tandem

Two on-device models, different jobs:

- **Executor** — Qwen 3.5 0.8B, NPU-pinned via QAIRT. Hot path. Executes, doesn't deliberate.
- **Query** — Qwen 3.5 9B Q4_0 via GenieX. Compiles meta-prompts, decides escalation, calls cloud tools.

**RAM math that makes this work:** 9B Q4_0 = ~5.45 GB weights + ~0.5-1 GB KV
cache = **~6-6.5 GB total**, against Alpha's 9-12 GB usable. That's the number.

**DISALLOW_NPU_OVERLAP** — the executor and query models must not both hold the
NPU. Enforced by `npu-inference-manager` (see `novus-aexenti`).

## Escalation order

on-device executor → on-device query (9B) → cheap cloud (GLM-5.2) → frontier.

Never skip to frontier for something the 9B can answer. Every frontier call is a
cost event and a data-egress event, both logged.
