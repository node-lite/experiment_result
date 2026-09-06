# NodeLite Live Validation Plan

This document records the remaining live measurement work that is not yet present in the current artifact set.

## 1. Real A->B Transition Measurements

Goal:

- Pick 20 representative profiles
- Measure 100-200 real A->B transitions
- Revalidate Phase 4 against actual wall-clock data

Target artifacts:

- `measured_pair_transitions.jsonl`
- `predicted_vs_measured.csv`
- `phase4_live_summary.md`

Success criteria:

- Real wall-clock A->B transition measurements exist for the selected pair set
- Prediction error is reported against actual measured transitions, not replay-derived oracles
- The sample set covers both low-overlap and high-reuse transitions

## 2. Real Scheduler Workload

Goal:

- Move beyond single-pass 64-profile replay
- Start with 500 tasks
- Expand to 2000+ tasks and keep the real task frequency distribution

Target artifacts:

- `live_scheduler_runs.csv`
- `live_transition_breakdown.csv`
- `phase5_live_summary.md`

Success criteria:

- FIFO, Random, Similarity, and NodeLite are compared on the same live workload
- The workload includes repeated profiles and skewed frequencies
- Decision overhead is measured on the live run, not replayed from prior data

## 3. Docker Warm-Image Baseline and Full Ablation

Goal:

- Measure Docker lifecycle separately from NodeLite reuse
- Compare:
  - Fresh Baseline
  - CTDP Only
  - CTDP + Reuse
  - Full NodeLite

Required sequence:

- `docker create`
- `docker start`
- semantic ready
- task
- `stop`
- `remove`

Target artifacts:

- `docker_baseline.csv`
- `ablation.csv`
- `final_ablation_summary.md`

Success criteria:

- Docker baseline is measured with an already-local image
- NodeLite and Docker are compared with the same task semantics
- Environment ready time, teardown time, A->B transition time, and total CPU-side time are reported

## Current Status

Not done yet. The current repository only contains replay / derived validation for Phase 3-7 and summary documents that describe those limitations explicitly.
