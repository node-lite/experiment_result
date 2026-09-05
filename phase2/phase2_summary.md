# Phase 2 Object / Action Latency Profiling

Status: **partial**

## Measurement Environment

- Environment ID: `env:7a9cda66bc6b151a7886`
- Host: `hydu8x5090gpu`
- CPU: `x86_64` / logical CPUs `384`
- OS/libc: `linux` / `glibc-2.39`
- Node/npm: `v22.23.2` / `10.9.8`
- Protocol: 2 warmups and 7 measurement samples per scenario where supported; summaries use median and P95.

## Catalog Coverage

- Benchmark catalog: `316 / 316` accounted
- Catalog coverage: `100.0%`
- Statuses: `{"blocked": 11, "manual_review": 7, "measured": 265, "not_applicable": 1, "unsupported": 32}`
- Raw observations: `5222`; active observations: `5152`
- Transition summaries: `736`

## Object Coverage

- All inventory objects: `33114`; Raw CAS objects are included for provenance but are not treated as scheduler resources.
- Scheduler-relevant exact objects from 64 RepoProfiles: `384`
- Exact measured relevant objects: `4` (`1.04%`)
- Relevant object statuses: `{"measured": 4, "unmeasured": 380}`
- direct_ms entries: `81`; FIFO window size `5`
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

## Key Measured Transitions

- Node: Node 18/20/22 cold start, exact hit, and all 3x3 directions are present in `node_switch_matrix.csv`.
- Package manager: npm, pnpm, Yarn Classic, Yarn Berry, and Bun exact-version observations are present in `pm_switch_matrix.csv`.
- Browser: Chromium and Firefox process/profile/context actions are measured; WebKit is explicitly unsupported on this host.
- Database: Redis daemon and SQLite snapshot/private-layer actions are measured; MongoDB/PostgreSQL/MySQL are explicitly unsupported because Docker/binaries are unavailable.
- Dependency view: generic PM fixtures plus one real SWE-smith Mongoose dependency view are measured; most real Profile-specific views remain unmeasured.
- Build/test/cache: measured fixture actions are retained with invalidation targets; missing tools and isolated host capabilities remain explicit gaps.

## Decision

Phase 2 is **partial**. The benchmark catalog is fully accounted for and the CostDB contains real 7-sample measurements, transition classes, invalidation rules, direct_ms windows, and host identity. It is not a full 64-Profile scheduler CostDB yet: most exact Profile-specific build/cache/dependency objects have no exact object_id observation, and blocked/unsupported host capabilities remain.

This output is suitable as a calibration CostDB and as the input to targeted completion work. It must not be interpreted as proof that every real Profile transition has been measured.

Generated from NodeLite-Schduler `out/`; catalog statuses and gaps are preserved in `catalog_status.json`, `coverage.md`, and `environment_gaps.md`.
