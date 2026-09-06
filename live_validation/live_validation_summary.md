# Live Validation Report

This directory contains the three live validation artifacts requested for the current pass.

## Live Pair Validation
- Selected profiles: `20`
- Directed pairs evaluated: `380`
- Sample pairs exported: `100`
- MAE: `8658.992` ms
- Pearson: `0.7631`

## Live Scheduler Validation
- Workload sizes: `500` and `2000` tasks
- Task source: `swe-smith_Task_IDs.csv`
- Scheduler runs exported: `18`

## Docker Validation
- Image: `node:20-slim`
- Modes exported: `4`

## Notes
- Pair and scheduler artifacts are derived from live exact-host measurements in `out/exact-workload`.
- Docker artifacts are measured directly on the warmed local image.
