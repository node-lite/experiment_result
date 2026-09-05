# Phase 1 CTDP Dependency Preparation Validation

Status: **partial**

## Coverage

- Profiles: 64 / 64
- Dependency roots: 65
- SWE-smith tasks in source CSV: 11105
- Package managers: `{"bun": 2, "npm": 33, "pnpm": 12, "yarn": 17}`

## Deduplication

- Dependency references: 101967
- Unique immutable artifacts: 33769
- Referenced bytes before dedup: 25309178036
- Unique CAS bytes after dedup: 17605669618
- Dedup ratio: 0.6688242274461346

## Network and Cache

- First-run network bytes: 9234461362
- Second-run network bytes: 3582234320
- Second-run result: 2766 downloaded, 29722 reused, 1 failed
- Warm-cache groups: 20 / 21 successful

## Real Install Validation

- Profile results: {'success': 18, 'external_artifact_miss': 16, 'native_or_system_dependency_failure': 0, 'other_failure': 30}
- Validation latency P50/P95/max (ms): 4414.5 / 44723.949999999975 / 69813
- Fresh and PM-cache comparison latency was not measured in Phase 1; the CSV records these fields as null.

## Decision

Phase 1 is **partial / not passed** under the strict plan criteria. CTDP completed the preparation pipeline across all 64 profiles and demonstrated cross-profile CAS deduplication, but resolution failures, one prefetch 404, partial Yarn classic warmup, install failures, and non-zero second-run network bytes remain.

The results support continuing to Phase 2 only with these limitations recorded; they do not support claiming zero-near-zero second-run traffic or full real-install success.

Generated: 2026-09-04T17:24:16.761564+00:00
