# Phase 6 Seed Priority Queue Validation (derived replay)

Status: **passed_with_constraints (derived replay)**

## Input
- Phase 5 schedule source: `phase5/nodelite_schedule.json`
- Phase 2 seed queue source: `phase2/seed_priority_queue.json`
- Age weight: `0.01`
- Random seeds: `11, 23, 37, 53, 71`

## Coverage
- Seed states: `5`
- Random runs per state: `5`
- Fallback-triggered states: `5`

## Main Results
- Random mean full remaining workload: `3772018.006` ms
- Fastest mean full remaining workload: `4583694.016` ms
- Degree mean full remaining workload: `2887614.514` ms
- Weighted Reach mean full remaining workload: `3333976.267` ms
- Weighted Reach vs Fastest delta: `1249717.749` ms
- Weighted Reach vs Degree delta: `-446361.753` ms
- Random stddev full remaining workload: `1920250.267` ms
- Weighted Reach mean reachable task count: `34.400`
- Weighted Reach mean reuse hit rate: `0.5152`
- Weighted Reach mean waiting time: `400000.000` s
- Starvation probe selected by Weighted Reach: `swesmith/GitbookIO__gitbook.81f8ddcf`
- Starvation probe age bonus override: `2000000.0` s
- Weighted Reach is best on full workload: `False`

## Validation Criteria
- Same candidate pool reused across policies within each snapshot: **Pass**
- Random baseline evaluated with 5 fixed seeds: **Pass**
- Age bonus changed the starvation probe outcome: **Pass**
- Seed choice affects reachable task count and full workload cost: **Pass**
- Weighted Reach beats both Fastest and Degree on full workload: **False**

## Unexpected Findings
- Fastest cold start can pick low-startup candidates with little future reuse, while Weighted Reach prefers larger reachable pools.
- In this replay, Weighted Reach beats Fastest but still trails Degree on full remaining workload.
- The starvation probe shows age bonus is strong enough to pull a queued seed back to the front when it has waited long enough.

## Generated Files
- `seed_states.json`
- `random_seed_results.csv`
- `fastest_seed_results.csv`
- `degree_seed_results.csv`
- `weighted_reach_results.csv`
- `starvation_analysis.csv`
- `phase6_summary.md`
- `phase6_summary.json`

## Remaining Problems
- This remains a derived replay over Phase 2 / Phase 5 data rather than a live host fallback exercise.
- The workload proxy is the Phase 5 `nodelite` order, so the phase still inherits the replay assumptions from earlier phases.

## Phase Decision
Phase 6 is **passed_with_constraints**.
