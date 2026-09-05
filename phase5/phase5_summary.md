# Phase 5 Resource-Aware Scheduling

Status: **passed_with_constraints**

## Input
- Phase 2 cost database: `env:7a9cda66bc6b151a7886`
- Phase 3 fixed task order: `phase3/fixed_task_sequence.json`
- Phase 4 validated pair cost model: `env:7a9cda66bc6b151a7886`
- Task count: `64`
- All non-FIFO schedulers are anchored to the same first profile so Phase 5 isolates ordering policy from Phase 6 seed selection.

## Coverage
- Scheduler runs: `8`
- Directed schedule transitions per run: `63`
- Random seeds: `11, 23, 37, 53, 71`

## Main Results
- FIFO measured transition time: `9514323.562` ms
- Similarity greedy measured transition time: `8449729.072` ms
- NodeLite cost greedy measured transition time: `8875263.447` ms
- Random mean measured transition time: `9492588.456` ms
- Random stddev measured transition time: `51760.171` ms
- FIFO makespan: `9531895.598` ms
- Similarity makespan: `8467301.108` ms
- NodeLite makespan: `8892835.483` ms
- Random mean makespan: `9510160.492` ms
- NodeLite vs FIFO savings: `639060.115` ms (`1.072x`)
- NodeLite vs Similarity savings: `-425534.375` ms (`0.952x`)
- NodeLite reuse hit rate: `0.1594`
- NodeLite depview rebuild count: `63`
- NodeLite browser restart count: `0`
- NodeLite DB restart count: `0`
- NodeLite invalidation cost: `8872061.464` ms
- NodeLite cleanup cost: `0.000` ms
- NodeLite decision overhead: `0.607` ms total / `0.009642` ms per decision

## Validation Criteria
- All schedulers executed the same task set: **Pass**
- No task dropped from any schedule: **Pass**
- NodeLite cost greedy completed with finite overhead: **Pass**
- Random baseline evaluated on 5 fixed seeds: **Pass**

## Unexpected Findings
- The fixed 64-profile SWE-smith slice does not contain browser or database resources, so those restart counts are zero for every scheduler.
- NodeLite cost greedy reduced total transition time by `639060.115` ms against FIFO and `-425534.375` ms against similarity greedy on this replay.

## Generated Files
- `fifo_schedule.json`
- `random_schedules/`
- `similarity_schedule.json`
- `nodelite_schedule.json`
- `scheduler_runs.csv`
- `transition_breakdown.csv`
- `decision_overhead.csv`
- `phase5_summary.md`
- `phase5_summary.json`

## Remaining Problems
- This phase is a derived replay over Phase 2 / Phase 3 / Phase 4 data rather than a fresh live host execution.
- The comparison is anchored on a fixed first profile so Phase 5 stays separate from the Phase 6 seed-selection study.

## Phase Decision
Phase 5 is **passed_with_constraints**.
