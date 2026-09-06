# POCKET-35B-GGUF — REJECTED

**Operator decision 2026-09-05.** Not adopted, not even as a cloud-tier fallback.

> *"that pocket is too big for the system"*

## The math

35B params x 0.5 bytes (Q4_0) ≈ **17.5 GB weights**, before KV cache.

| Node | RAM | Fits? |
|---|---|---|
| Alpha (Moto Razr) | 9-12 GB usable | **No** |
| Beta (Jetson Orin Nano) | 8 GB LPDDR5 | **No** — smaller than Alpha |
| Delta (GCP) | arbitrary | technically yes |

Cloud-tier would work, but the operator ruled it out rather than add a model
that can never come home to the edge. Gemma 4 12B took the roster slot instead.

## Do not re-propose

without new hardware that changes the RAM ceiling.
