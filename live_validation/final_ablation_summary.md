# Docker Warm-Image Baseline and Ablation

Status: **live_host_measured**

- Docker image: `node:20-slim`
- Samples per mode: `5`

## Aggregates
- fresh_baseline: total median `10459.536` ms, ready median `70.071` ms, task median `77.364` ms
- ctdp_only: total median `10466.284` ms, ready median `73.555` ms, task median `51.062` ms
- ctdp_plus_reuse: total median `10450.990` ms, ready median `69.603` ms, task median `54.506` ms
- full_nodelite: total median `10467.978` ms, ready median `74.965` ms, task median `74.770` ms

## Notes
- Baseline and ablation are measured on a warmed local `node:20-slim` image.
- CTDP and exact-workload directories are mounted read-only for the derived modes.
- This is a live Docker run, not a replay artifact.
