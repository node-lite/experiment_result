# Phase 3 Resource Reuse Validation (derived replay)

Status: **passed_with_constraints (derived replay)**

## Input

- Phase 2 CostDB and object/action summary from `experiment_result/phase2/`.
- Fixed 64-profile task order from `CTDP/swe_smith_64_project_ids.txt`.
- Profile resource signatures from `phase2/profile_requirements.json` and `phase2/inventory.json`.

## Coverage

- Task count: `64`
- Resource actions in fixed sequence: `493`
- Exact object-backed action spans: `315`
- Same-kind proxy action spans: `178`
- Source environment IDs used by the merged input: `["env:0fd7b54e0a2a55d4208d", "env:7a9cda66bc6b151a7886"]`

## Main Results

- Fresh median / P95: `116342.056` ms / `299053.075` ms
- Reuse median / P95: `366.317` ms / `11759.893` ms
- Total Fresh transition time: `8028246.815` ms
- Total Reuse transition time: `144898.131` ms
- Total saved time: `7883348.685` ms
- Speedup: `55.41x`
- Cache reuse hit rate: `488/493` (`98.99%`)
- Cleanup / reset cost: `0.353` ms
- Browser restart reduction: `0` (the fixed 64-profile SWE-smith slice does not include browser resources)
- DB restart reduction: `0` (the fixed 64-profile SWE-smith slice does not include database resources)
- Depview rematerialization reduction: `65` actions, `1023754.553` ms saved
- Pollution failures: `0`
- Correctness mismatches: `0`

## Per Resource Kind

| Resource kind | Actions | Exact | Proxy | Reuse hits | Hit rate | Fresh saved ms |
|---|---:|---:|---:|---:|---:|---:|
| `build_cache` | 85 | 15 | 70 | 85 | 100.00% | 6439481.307 |
| `dependency_view` | 65 | 33 | 32 | 65 | 100.00% | 1023754.553 |
| `test_transform_cache` | 70 | 9 | 61 | 70 | 100.00% | 400885.632 |
| `native_binary_bundle` | 16 | 5 | 11 | 11 | 68.75% | 7365.406 |
| `node_runtime` | 64 | 62 | 2 | 64 | 100.00% | 3836.304 |
| `repo_baseline` | 64 | 64 | 0 | 64 | 100.00% | 3561.293 |
| `rootfs` | 64 | 62 | 2 | 64 | 100.00% | 2249.437 |
| `source_overlay` | 65 | 65 | 0 | 65 | 100.00% | 2214.752 |

## Validation Criteria

- Fresh 与 Reuse 使用完全相同 task order: **Pass**
- 所有 reuse path 通过 isolation/correctness: **Pass**
- pollution failure 数: **0**
- correctness mismatch 数: **0**
- 178 个 action span 采用 same-kind proxy fallback，但没有引入污染或顺序漂移: **Constraint only**

## Unexpected Findings

- 64 个 profile 一共展开成 493 个 resource actions，其中 315 个直接来自 exact object-backed measurements，178 个来自同类 resource-kind proxy fallback。
- 5 个 native binary bundle action 没有独立的 reuse-safe hit，仍保持 cold load 语义。
- Browser / DB 类资源不在这 64-profile 固定序列中，因此对应 restart reduction 为 0。

## Generated Files

- `fixed_task_sequence.json`
- `fresh_transitions.jsonl`
- `reuse_transitions.jsonl`
- `action_spans.jsonl`
- `correctness.csv`
- `pollution_failures.json`
- `fresh_vs_reuse.csv`

## Remaining Problems

- This phase is a derived replay over Phase 2 CostDB, not a new live host run.
- Some resource actions rely on same-kind proxy fallback because the exact object-level summary row is missing from the Phase 2 merged data.

## Phase Decision

Phase 3 is **passed_with_constraints**.
