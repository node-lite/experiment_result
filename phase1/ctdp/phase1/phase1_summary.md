# Phase 1 CTDP Dependency Preparation Validation

Status: **partial**

## Coverage

- Profiles: 64 / 64
- Dependency roots: 65
- SWE-smith tasks in source CSV: not available
- Package managers: `{"bun": 2, "npm": 33, "pnpm": 12, "yarn": 17}`

## Deduplication

- Dependency references: 105097
- Unique immutable artifacts: 34462
- Referenced bytes before dedup: 25418483974
- Unique CAS bytes after dedup: 17672905706
- Dedup ratio: 0.6720933994310019

## Network and Cache

- First-run network bytes: 9234461362
- Second-run network bytes: 213832627
- Second-run result: 397 downloaded, 32543 reused, 1 failed
- Warm-cache groups: 20 / 21 successful

## Real Install Validation

- Profile results: {'success': 19, 'external_artifact_miss': 30, 'native_or_system_dependency_failure': 3, 'other_failure': 12}
- Validation latency P50/P95/max (ms): 6574.5 / 54508.049999999945 / 138745
- Fresh and PM-cache comparison latency was not measured in Phase 1; the CSV records these fields as null.

## Targeted External Artifact Revalidation

- Scope: 21 profiles from the original `external_artifact_miss` set, covering 10 registry/proxy cases, 5 CAS tarball cases, and 6 Git/VCS cases.
- G1 preparation and local-registry install: 21 / 21 successful.
- External artifact misses after the targeted rerun: 0 / 21.
- Outbound requests observed during the targeted rerun: 0.
- Evidence: `phase1/external_artifact_revalidation.json`.
- This is a targeted G1 revalidation, not a replacement for the full 64-profile G2 lifecycle/build validation. The baseline `validation.json` remains unchanged and is reported above for traceability.

## Decision

Phase 1 is **partial / not passed** under the strict plan criteria. The targeted rerun resolved the 21 selected external-artifact preparation failures, demonstrating that the local registry, CAS fallback, and Git/VCS handling work for those cases. The complete 64-profile G2 validation still has 12 unresolved profiles, and the baseline preparation run still records partial Yarn classic warmup and non-zero second-run network bytes.

The results support continuing to Phase 2 only with these limitations recorded; they do not support claiming zero-near-zero second-run traffic or full real-install success. The targeted result must not be aggregated with the baseline 64-profile result as though all profiles had completed the same validation path.

Generated: 2026-09-05T11:38:00.366402+00:00
Updated: 2026-09-05T12:20:00+00:00
