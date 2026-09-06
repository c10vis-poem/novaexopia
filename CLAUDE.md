# NovÆxopia — tools, harness, and engine layer

Canon name: **NovÆxopia**. Repo name: `novaexopia`. See `novae-xorpus/NAMING-CANON.md`.

## What this is

The action surface of the Æsop-Xi stack — what the agent (NovÆxenti) can
actually do. Contains inference engine configs, model weight management,
runtime definitions, and tool-skill wiring. Supersedes the earlier "Omni Claw"
/ "NovA-Claw" / "NovÆcopia" naming.

## Stack position

```
Æsop-Xi          infrastructure (MCPs, hooks, memory, routing, protocols)
  └─ NovÆxenti   agent logic — executor + query cores
       └─ NovÆxopia   tools, harness, engine (this repo)
            ├─ Æsc         terminal daemon
            └─ Æyre        voice / vision daemon
```

## Conventions

- Engine configs in `engines/` — one file per inference backend (llama.cpp,
  QAIRT, cloud API).
- Runtime definitions in `runtimes/` — how a model is loaded and served.
- Weight manifests in `weights/` — model metadata, quantization specs, device
  compatibility. Actual weight files are NOT stored in git.
- `config/` holds cross-cutting settings (temperature defaults, token limits,
  routing rules).
- `manifest.jsonl` is the machine-readable index.

## Git workflow

PR required. No direct pushes to main. CI runs gitleaks + structure check.
