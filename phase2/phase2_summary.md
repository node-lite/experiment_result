# Phase 2 Object / Action Latency Profiling

Status: **passed_with_constraints**

## Measurement Environment

- Environment ID: `env:7a9cda66bc6b151a7886`
- Environment IDs represented in observations: `["env:0fd7b54e0a2a55d4208d", "env:7a9cda66bc6b151a7886"]`
- Host: `hydu8x5090gpu`
- CPU: `x86_64` / logical CPUs `384`
- OS/libc: `linux` / `glibc-2.39`
- Node/npm: `v22.23.2` / `10.9.8`
- Protocol: 2 warmups and 7 measurement samples per scenario where supported; summaries use median and P95.
- Cross-host policy: summary rows retain `measurement_environment_id`; `direct_ms_by_environment.json` prevents silent cross-host averaging.

## Catalog Coverage

- Benchmark catalog: `316 / 316` accounted
- Catalog coverage: `100.0%`
- Statuses: `{"blocked": 11, "manual_review": 7, "measured": 265, "not_applicable": 1, "unsupported": 32}`
- Raw/active observations after exact merge: `5306` / `5236`
- Transition summaries after exact merge: `748`

## Object Coverage

- All inventory objects: `33114`; Raw CAS objects are included for provenance but are not treated as scheduler resources.
- Scheduler-relevant exact objects from 64 RepoProfiles: `384`
- Exact measured relevant objects: `8` (`2.08%`)
- Relevant object statuses: `{"blocked": 363, "manual_review": 13, "measured": 8}`
- direct_ms entries: `81`; FIFO window size `5`
- Current-host exact direct_ms entries: `4` in `exact_workload/direct_ms.json`
- Generic synthetic actions are retained as calibration evidence but are not counted as exact measurements for a real Profile object.

## Resource Kinds

- `artifact_acquisition`: `7`
- `browser_binary`: `3`
- `browser_context`: `3`
- `browser_process`: `3`
- `browser_profile`: `3`
- `build_cache`: `97`
- `contention`: `10`
- `control_plane`: `12`
- `database_binary`: `5`
- `database_clean_snapshot`: `5`
- `database_daemon`: `4`
- `database_private_layer`: `5`
- `dependency_view`: `90`
- `discovery_resolution`: `18`
- `display_service`: `3`
- `failure_recovery`: `12`
- `filesystem_overlay`: `1`
- `home_tmp_xdg`: `2`
- `local_registry`: `9`
- `native_binary_bundle`: `22`
- `network_ports`: `1`
- `node_runtime`: `7`
- `package_manager`: `24`
- `pm_native_cache`: `24`
- `project_server`: `3`
- `raw_cas`: `32502`
- `repo_baseline`: `64`
- `rootfs`: `16`
- `source_overlay`: `77`
- `system_toolchain`: `1`
- `task_harness`: `1`
- `test_transform_cache`: `80`

## Exact Workload Status

| Resource kind | Measured | Blocked | Unsupported | Manual review | Failed |
|---|---:|---:|---:|---:|---:|
| `build_cache` | 0 | 85 | 0 | 0 | 0 |
| `dependency_view` | 5 | 48 | 0 | 12 | 0 |
| `native_binary_bundle` | 0 | 16 | 0 | 0 | 0 |
| `node_runtime` | 3 | 0 | 0 | 1 | 0 |
| `repo_baseline` | 0 | 64 | 0 | 0 | 0 |
| `rootfs` | 0 | 15 | 0 | 0 | 0 |
| `source_overlay` | 0 | 65 | 0 | 0 | 0 |
| `test_transform_cache` | 0 | 70 | 0 | 0 | 0 |

## Exact Dependency Measurements

| Object | Action | Median ms | P95 ms | Samples | Environment |
|---|---|---:|---:|---:|---|
| `dependency_view:foambubble__foam.2cac8162:root:8118db77d559a658` | `EXACT-DEP-ATTACH` | 0.575 | 0.587 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:foambubble__foam.2cac8162:root:8118db77d559a658` | `EXACT-DEP-MATERIALIZE` | 5856.184 | 6505.074 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:foambubble__foam.2cac8162:root:8118db77d559a658` | `EXACT-DEP-RESET` | 0.024 | 0.029 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:jaredpalmer__formik.91475adb:root:0ea1f56b0c1e2753` | `EXACT-DEP-ATTACH` | 0.263 | 0.349 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:jaredpalmer__formik.91475adb:root:0ea1f56b0c1e2753` | `EXACT-DEP-MATERIALIZE` | 5837.947 | 8137.201 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:jaredpalmer__formik.91475adb:root:0ea1f56b0c1e2753` | `EXACT-DEP-RESET` | 0.027 | 0.035 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:redux-saga__redux-saga.a4ace10d:root:c1bcbd93da3b0eeb` | `EXACT-DEP-ATTACH` | 1.135 | 1.227 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:redux-saga__redux-saga.a4ace10d:root:c1bcbd93da3b0eeb` | `EXACT-DEP-MATERIALIZE` | 9529.210 | 10090.261 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:redux-saga__redux-saga.a4ace10d:root:c1bcbd93da3b0eeb` | `EXACT-DEP-RESET` | 0.025 | 0.029 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:sveltejs__svelte.6c9717a9:root:b0c07bc3f3203c46` | `EXACT-DEP-ATTACH` | 0.062 | 0.067 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:sveltejs__svelte.6c9717a9:root:b0c07bc3f3203c46` | `EXACT-DEP-MATERIALIZE` | 1802.468 | 1824.576 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:sveltejs__svelte.6c9717a9:root:b0c07bc3f3203c46` | `EXACT-DEP-RESET` | 0.024 | 0.025 | 7 | `env:0fd7b54e0a2a55d4208d` |

## Key Measured Transitions

- Node: Node 18/20/22 cold start, exact hit, and all 3x3 directions are present in `node_switch_matrix.csv`.
- Package manager: npm, pnpm, Yarn Classic, Yarn Berry, and Bun exact-version observations are present in `pm_switch_matrix.csv`.
- Browser: Chromium and Firefox process/profile/context actions are measured; WebKit is explicitly unsupported on this host.
- Database: Redis daemon and SQLite snapshot/private-layer actions are measured; MongoDB/PostgreSQL/MySQL are explicitly unsupported because Docker/binaries are unavailable.
- Dependency view exact run: `{"blocked": 48, "manual_review": 12, "measured": 4}`.
- Repo/source/build/test/native/rootfs exact statuses: see `unmeasured_objects.json`; no object remains implicit (`unmeasured=0`).

## Decision

Phase 2 is **passed_with_constraints**. Every scheduler-relevant exact object is measured or has an explicit blocked/unsupported/manual-review/failed status. Blocked objects are accounted, but they are not latency measurements and must not be treated as zero.

This output is suitable as a calibration CostDB and as the input to targeted completion work. It must not be interpreted as proof that every real Profile transition has been measured.

Generated from NodeLite-Schduler `out/`; catalog statuses and gaps are preserved in `catalog_status.json`, `coverage.md`, and `environment_gaps.md`.
