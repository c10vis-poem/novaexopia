# Qwen 3.5 9B

**Slug:** `qwen-3.5-9b-unsloth-gguf-q4_0` · **Status:** ACTIVE

| Field | Value |
|---|---|
| Quantization | GGUF Q4_0 (Unsloth) |
| Size | ~5.45 GB weights + ~0.5-1 GB KV = ~6-6.5 GB total |
| Target node | Alpha / NPU via GenieX |
| Role | query |

## Notes

The thinking half. Fits Alpha's 9-12 GB usable. This RAM math is what makes on-device 9B viable.
