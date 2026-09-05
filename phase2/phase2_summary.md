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
- Raw/active observations after exact merge: `8589` / `8322`
- Transition summaries after exact merge: `1190`

## Object Coverage

- All inventory objects: `33114`; Raw CAS objects are included for provenance but are not treated as scheduler resources.
- Scheduler-relevant exact objects from 64 RepoProfiles: `384`
- Exact measured relevant objects: `207` (`53.91%`)
- Relevant object statuses: `{"blocked": 102, "manual_review": 75, "measured": 207}`
- direct_ms entries: `81`; FIFO window size `5`
- Current-host exact direct_ms entries: `204` in `exact_workload/direct_ms.json`
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
| `build_cache` | 15 | 34 | 0 | 36 | 0 |
| `dependency_view` | 32 | 21 | 0 | 12 | 0 |
| `native_binary_bundle` | 5 | 11 | 0 | 0 | 0 |
| `node_runtime` | 3 | 0 | 0 | 1 | 0 |
| `repo_baseline` | 64 | 0 | 0 | 0 | 0 |
| `rootfs` | 14 | 0 | 0 | 1 | 0 |
| `source_overlay` | 65 | 0 | 0 | 0 | 0 |
| `test_transform_cache` | 9 | 36 | 0 | 25 | 0 |

## Exact Dependency Measurements

| Object | Action | Median ms | P95 ms | Samples | Environment |
|---|---|---:|---:|---:|---|
| `build_cache:Effect-TS__effect.5df4da10:root:typescript:3936ee7940b9` | `EXACT-BUILD-CACHE-COLD` | 16499.730 | 16782.631 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:Effect-TS__effect.5df4da10:root:typescript:3936ee7940b9` | `EXACT-BUILD-CACHE-HIT` | 16682.561 | 16829.535 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:Shopify__draggable.8a1eed57:root:rollup:75fa7c4af02e` | `EXACT-BUILD-CACHE-COLD` | 5060.622 | 5241.943 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:Shopify__draggable.8a1eed57:root:rollup:75fa7c4af02e` | `EXACT-BUILD-CACHE-HIT` | 5043.648 | 5107.518 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:Shopify__draggable.8a1eed57:root:typescript:75fa7c4af02e` | `EXACT-BUILD-CACHE-COLD` | 284.293 | 285.740 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:Shopify__draggable.8a1eed57:root:typescript:75fa7c4af02e` | `EXACT-BUILD-CACHE-HIT` | 283.862 | 290.250 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:brianc__node-postgres.ecff60dc:root:typescript:f43ed1faaa9b` | `EXACT-BUILD-CACHE-COLD` | 274.781 | 278.290 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:brianc__node-postgres.ecff60dc:root:typescript:f43ed1faaa9b` | `EXACT-BUILD-CACHE-HIT` | 274.294 | 300.103 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:foambubble__foam.2cac8162:root:lerna:2510f8df8165` | `EXACT-BUILD-CACHE-COLD` | 3245.389 | 3443.076 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:foambubble__foam.2cac8162:root:lerna:2510f8df8165` | `EXACT-BUILD-CACHE-HIT` | 2821.352 | 2887.465 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:josdejong__jsoneditor.0319b213:root:gulp:be56cc981d38` | `EXACT-BUILD-CACHE-COLD` | 11257.798 | 11493.543 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:josdejong__jsoneditor.0319b213:root:gulp:be56cc981d38` | `EXACT-BUILD-CACHE-HIT` | 11147.650 | 11451.540 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:josdejong__mathjs.04e6e2d7:root:gulp:4c7f724eabb4` | `EXACT-BUILD-CACHE-COLD` | 22559.433 | 22623.419 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:josdejong__mathjs.04e6e2d7:root:gulp:4c7f724eabb4` | `EXACT-BUILD-CACHE-HIT` | 22661.084 | 22827.508 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:josdejong__mathjs.04e6e2d7:root:typescript:4c7f724eabb4` | `EXACT-BUILD-CACHE-COLD` | 8413.023 | 8443.524 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:josdejong__mathjs.04e6e2d7:root:typescript:4c7f724eabb4` | `EXACT-BUILD-CACHE-HIT` | 8350.876 | 8607.552 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:payloadcms__payload.8f660355:root:turbo:096d4a336345` | `EXACT-BUILD-CACHE-COLD` | 89601.622 | 91869.686 | 5 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:payloadcms__payload.8f660355:root:turbo:096d4a336345` | `EXACT-BUILD-CACHE-HIT` | 7271.141 | 7500.902 | 5 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:refined-github__refined-github.d4a7c3fb:root:rollup:aa1f302ca640` | `EXACT-BUILD-CACHE-COLD` | 2998.650 | 3021.669 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:refined-github__refined-github.d4a7c3fb:root:rollup:aa1f302ca640` | `EXACT-BUILD-CACHE-HIT` | 2990.436 | 3121.777 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:refined-github__refined-github.d4a7c3fb:root:typescript:aa1f302ca640` | `EXACT-BUILD-CACHE-COLD` | 3839.764 | 3907.235 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:refined-github__refined-github.d4a7c3fb:root:typescript:aa1f302ca640` | `EXACT-BUILD-CACHE-HIT` | 3843.117 | 3909.175 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:tinacms__tinacms.dffb104f:root:turbo:765d0508e257` | `EXACT-BUILD-CACHE-COLD` | 15924.306 | 16010.528 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:tinacms__tinacms.dffb104f:root:turbo:765d0508e257` | `EXACT-BUILD-CACHE-HIT` | 1277.604 | 1365.801 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:trpc__trpc.2f40ba93:root:turbo:8fa8b4550448` | `EXACT-BUILD-CACHE-COLD` | 23082.375 | 23313.633 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:trpc__trpc.2f40ba93:root:turbo:8fa8b4550448` | `EXACT-BUILD-CACHE-HIT` | 9756.161 | 10067.748 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:ueberdosis__tiptap.2d6de06c:root:turbo:85ad102bc603` | `EXACT-BUILD-CACHE-COLD` | 68447.668 | 69093.069 | 5 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:ueberdosis__tiptap.2d6de06c:root:turbo:85ad102bc603` | `EXACT-BUILD-CACHE-HIT` | 3502.893 | 3601.171 | 5 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:voideditor__void.17e7a5b1:root:typescript:0426f7949e03` | `EXACT-BUILD-CACHE-COLD` | 11447.801 | 11570.838 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `build_cache:voideditor__void.17e7a5b1:root:typescript:0426f7949e03` | `EXACT-BUILD-CACHE-HIT` | 11553.336 | 11697.063 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:Effect-TS__effect.5df4da10:root:61e1a82d9173e1a4` | `EXACT-DEP-ATTACH` | 0.080 | 0.092 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:Effect-TS__effect.5df4da10:root:61e1a82d9173e1a4` | `EXACT-DEP-MATERIALIZE` | 2353.256 | 2475.406 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:Effect-TS__effect.5df4da10:root:61e1a82d9173e1a4` | `EXACT-DEP-RESET` | 0.019 | 0.023 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:FuelLabs__fuels-ts.b3f37c91:root:471ddc5c5a27de32` | `EXACT-DEP-ATTACH` | 0.116 | 0.131 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:FuelLabs__fuels-ts.b3f37c91:root:471ddc5c5a27de32` | `EXACT-DEP-MATERIALIZE` | 6518.345 | 6630.499 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:FuelLabs__fuels-ts.b3f37c91:root:471ddc5c5a27de32` | `EXACT-DEP-RESET` | 0.020 | 0.023 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:NativeScript__NativeScript.3d6a4392:root:085e1f7ccbe42f25` | `EXACT-DEP-ATTACH` | 1.193 | 1.253 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:NativeScript__NativeScript.3d6a4392:root:085e1f7ccbe42f25` | `EXACT-DEP-MATERIALIZE` | 8734.230 | 10177.711 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:NativeScript__NativeScript.3d6a4392:root:085e1f7ccbe42f25` | `EXACT-DEP-RESET` | 0.020 | 0.032 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:ReactiveX__rxjs.c15b37f8:root:c5fbb2e88b68c3b9` | `EXACT-DEP-ATTACH` | 1.844 | 1.892 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:ReactiveX__rxjs.c15b37f8:root:c5fbb2e88b68c3b9` | `EXACT-DEP-MATERIALIZE` | 26502.239 | 26895.266 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:ReactiveX__rxjs.c15b37f8:root:c5fbb2e88b68c3b9` | `EXACT-DEP-RESET` | 0.020 | 0.035 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:Shopify__draggable.8a1eed57:root:5951b44524aa69b1` | `EXACT-DEP-ATTACH` | 0.891 | 0.979 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:Shopify__draggable.8a1eed57:root:5951b44524aa69b1` | `EXACT-DEP-MATERIALIZE` | 4341.950 | 4400.689 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:Shopify__draggable.8a1eed57:root:5951b44524aa69b1` | `EXACT-DEP-RESET` | 0.031 | 0.039 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:advplyr__audiobookshelf.626596b1:client:53df8633198c6f33` | `EXACT-DEP-ATTACH` | 1.256 | 1.445 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:advplyr__audiobookshelf.626596b1:client:53df8633198c6f33` | `EXACT-DEP-MATERIALIZE` | 6664.384 | 6847.684 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:advplyr__audiobookshelf.626596b1:client:53df8633198c6f33` | `EXACT-DEP-RESET` | 0.031 | 0.037 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:advplyr__audiobookshelf.626596b1:root:671774675e08f64e` | `EXACT-DEP-ATTACH` | 0.547 | 0.596 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:advplyr__audiobookshelf.626596b1:root:671774675e08f64e` | `EXACT-DEP-MATERIALIZE` | 2238.428 | 2297.787 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:advplyr__audiobookshelf.626596b1:root:671774675e08f64e` | `EXACT-DEP-RESET` | 0.032 | 0.042 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:brianc__node-postgres.ecff60dc:root:ac69cf7675d96f1d` | `EXACT-DEP-ATTACH` | 1.092 | 1.098 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:brianc__node-postgres.ecff60dc:root:ac69cf7675d96f1d` | `EXACT-DEP-MATERIALIZE` | 6766.343 | 7406.071 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:brianc__node-postgres.ecff60dc:root:ac69cf7675d96f1d` | `EXACT-DEP-RESET` | 0.022 | 0.031 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:caolan__async.23dbf76a:root:579fe631d378a055` | `EXACT-DEP-ATTACH` | 0.835 | 0.894 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:caolan__async.23dbf76a:root:579fe631d378a055` | `EXACT-DEP-MATERIALIZE` | 3035.551 | 3197.941 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:caolan__async.23dbf76a:root:579fe631d378a055` | `EXACT-DEP-RESET` | 0.021 | 0.037 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:coder__code-server.e90504b8:root:cc86648d271cc663` | `EXACT-DEP-ATTACH` | 0.582 | 0.609 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:coder__code-server.e90504b8:root:cc86648d271cc663` | `EXACT-DEP-MATERIALIZE` | 1796.624 | 1926.976 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:coder__code-server.e90504b8:root:cc86648d271cc663` | `EXACT-DEP-RESET` | 0.031 | 0.040 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:fabricjs__fabric.js.6742471c:root:56b6543f933cb2b3` | `EXACT-DEP-ATTACH` | 0.596 | 0.617 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:fabricjs__fabric.js.6742471c:root:56b6543f933cb2b3` | `EXACT-DEP-MATERIALIZE` | 3085.353 | 3324.007 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:fabricjs__fabric.js.6742471c:root:56b6543f933cb2b3` | `EXACT-DEP-RESET` | 0.022 | 0.029 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:foambubble__foam.2cac8162:root:8118db77d559a658` | `EXACT-DEP-ATTACH` | 0.575 | 0.587 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:foambubble__foam.2cac8162:root:8118db77d559a658` | `EXACT-DEP-MATERIALIZE` | 5856.184 | 6505.074 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:foambubble__foam.2cac8162:root:8118db77d559a658` | `EXACT-DEP-RESET` | 0.024 | 0.029 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:homebridge__homebridge.3a341e08:root:5aba58d9ad81636b` | `EXACT-DEP-ATTACH` | 0.624 | 0.673 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:homebridge__homebridge.3a341e08:root:5aba58d9ad81636b` | `EXACT-DEP-MATERIALIZE` | 2508.447 | 2722.985 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:homebridge__homebridge.3a341e08:root:5aba58d9ad81636b` | `EXACT-DEP-RESET` | 0.020 | 0.035 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:humanlayer__12-factor-agents.d20c7283:packages_walkthroughgen:231f2c674eecc38e` | `EXACT-DEP-ATTACH` | 0.315 | 0.349 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:humanlayer__12-factor-agents.d20c7283:packages_walkthroughgen:231f2c674eecc38e` | `EXACT-DEP-MATERIALIZE` | 1722.880 | 1854.819 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:humanlayer__12-factor-agents.d20c7283:packages_walkthroughgen:231f2c674eecc38e` | `EXACT-DEP-RESET` | 0.028 | 0.035 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:iamkun__dayjs.c8a26460:root:c68f1e093a72eecf` | `EXACT-DEP-ATTACH` | 1.235 | 1.452 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:iamkun__dayjs.c8a26460:root:c68f1e093a72eecf` | `EXACT-DEP-MATERIALIZE` | 6871.276 | 10185.247 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:iamkun__dayjs.c8a26460:root:c68f1e093a72eecf` | `EXACT-DEP-RESET` | 0.027 | 0.036 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:jaredpalmer__formik.91475adb:root:0ea1f56b0c1e2753` | `EXACT-DEP-ATTACH` | 0.263 | 0.349 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:jaredpalmer__formik.91475adb:root:0ea1f56b0c1e2753` | `EXACT-DEP-MATERIALIZE` | 5837.947 | 8137.201 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:jaredpalmer__formik.91475adb:root:0ea1f56b0c1e2753` | `EXACT-DEP-RESET` | 0.027 | 0.035 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:josdejong__jsoneditor.0319b213:root:fba013e11b2e4bd9` | `EXACT-DEP-ATTACH` | 0.745 | 0.851 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:josdejong__jsoneditor.0319b213:root:fba013e11b2e4bd9` | `EXACT-DEP-MATERIALIZE` | 2580.545 | 2692.343 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:josdejong__jsoneditor.0319b213:root:fba013e11b2e4bd9` | `EXACT-DEP-RESET` | 0.019 | 65.596 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:josdejong__mathjs.04e6e2d7:root:653bb0be0a5e4b8c` | `EXACT-DEP-ATTACH` | 0.956 | 1.000 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:josdejong__mathjs.04e6e2d7:root:653bb0be0a5e4b8c` | `EXACT-DEP-MATERIALIZE` | 3325.814 | 3369.975 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:josdejong__mathjs.04e6e2d7:root:653bb0be0a5e4b8c` | `EXACT-DEP-RESET` | 0.038 | 0.042 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:microsoft__vscode.4166e90a:root:ebafff009f16e711` | `EXACT-DEP-ATTACH` | 1.114 | 1.147 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:microsoft__vscode.4166e90a:root:ebafff009f16e711` | `EXACT-DEP-MATERIALIZE` | 4645.553 | 4726.325 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:microsoft__vscode.4166e90a:root:ebafff009f16e711` | `EXACT-DEP-RESET` | 0.020 | 0.039 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:nightwatchjs__nightwatch.54c8550c:root:4a947b8a3bf39687` | `EXACT-DEP-ATTACH` | 0.784 | 0.873 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:nightwatchjs__nightwatch.54c8550c:root:4a947b8a3bf39687` | `EXACT-DEP-MATERIALIZE` | 4207.160 | 4353.518 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:nightwatchjs__nightwatch.54c8550c:root:4a947b8a3bf39687` | `EXACT-DEP-RESET` | 0.022 | 0.035 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:nock__nock.e7418da2:root:541f81ce3f744a6f` | `EXACT-DEP-ATTACH` | 0.861 | 0.950 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:nock__nock.e7418da2:root:541f81ce3f744a6f` | `EXACT-DEP-MATERIALIZE` | 4012.563 | 4179.981 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:nock__nock.e7418da2:root:541f81ce3f744a6f` | `EXACT-DEP-RESET` | 0.036 | 64.529 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:payloadcms__payload.8f660355:root:a2f282bd4e00dd49` | `EXACT-DEP-ATTACH` | 0.113 | 0.177 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:payloadcms__payload.8f660355:root:a2f282bd4e00dd49` | `EXACT-DEP-MATERIALIZE` | 5676.723 | 5770.087 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:payloadcms__payload.8f660355:root:a2f282bd4e00dd49` | `EXACT-DEP-RESET` | 0.020 | 0.025 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:redux-saga__redux-saga.a4ace10d:root:c1bcbd93da3b0eeb` | `EXACT-DEP-ATTACH` | 1.135 | 1.227 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:redux-saga__redux-saga.a4ace10d:root:c1bcbd93da3b0eeb` | `EXACT-DEP-MATERIALIZE` | 9529.210 | 10090.261 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:redux-saga__redux-saga.a4ace10d:root:c1bcbd93da3b0eeb` | `EXACT-DEP-RESET` | 0.025 | 0.029 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:refined-github__refined-github.d4a7c3fb:root:e375b9cbe15b1aee` | `EXACT-DEP-ATTACH` | 0.712 | 0.804 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:refined-github__refined-github.d4a7c3fb:root:e375b9cbe15b1aee` | `EXACT-DEP-MATERIALIZE` | 2906.534 | 3007.747 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:refined-github__refined-github.d4a7c3fb:root:e375b9cbe15b1aee` | `EXACT-DEP-RESET` | 0.021 | 0.027 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:remy__nodemon.daad5c16:root:e2111c2b7033d511` | `EXACT-DEP-ATTACH` | 0.525 | 0.578 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:remy__nodemon.daad5c16:root:e2111c2b7033d511` | `EXACT-DEP-MATERIALIZE` | 2871.139 | 2981.433 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:remy__nodemon.daad5c16:root:e2111c2b7033d511` | `EXACT-DEP-RESET` | 0.020 | 0.023 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:sveltejs__svelte.6c9717a9:root:b0c07bc3f3203c46` | `EXACT-DEP-ATTACH` | 0.062 | 0.067 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:sveltejs__svelte.6c9717a9:root:b0c07bc3f3203c46` | `EXACT-DEP-MATERIALIZE` | 1802.468 | 1824.576 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:sveltejs__svelte.6c9717a9:root:b0c07bc3f3203c46` | `EXACT-DEP-RESET` | 0.024 | 0.025 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:tinacms__tinacms.dffb104f:root:45f79d9b7f2dc887` | `EXACT-DEP-ATTACH` | 0.074 | 0.082 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:tinacms__tinacms.dffb104f:root:45f79d9b7f2dc887` | `EXACT-DEP-MATERIALIZE` | 7700.718 | 7896.667 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:tinacms__tinacms.dffb104f:root:45f79d9b7f2dc887` | `EXACT-DEP-RESET` | 0.019 | 0.024 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:trpc__trpc.2f40ba93:root:781fb8f3cbe882e8` | `EXACT-DEP-ATTACH` | 0.086 | 0.091 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:trpc__trpc.2f40ba93:root:781fb8f3cbe882e8` | `EXACT-DEP-MATERIALIZE` | 9480.072 | 9791.083 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:trpc__trpc.2f40ba93:root:781fb8f3cbe882e8` | `EXACT-DEP-RESET` | 0.020 | 0.021 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:ueberdosis__tiptap.2d6de06c:root:0bd9814a60fd8695` | `EXACT-DEP-ATTACH` | 0.097 | 0.144 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:ueberdosis__tiptap.2d6de06c:root:0bd9814a60fd8695` | `EXACT-DEP-MATERIALIZE` | 1872.153 | 1904.172 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:ueberdosis__tiptap.2d6de06c:root:0bd9814a60fd8695` | `EXACT-DEP-RESET` | 0.019 | 0.026 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:vitejs__vite.8b47ff76:root:7fb655fa88697a9a` | `EXACT-DEP-ATTACH` | 0.072 | 0.078 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:vitejs__vite.8b47ff76:root:7fb655fa88697a9a` | `EXACT-DEP-MATERIALIZE` | 2247.363 | 2645.924 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:vitejs__vite.8b47ff76:root:7fb655fa88697a9a` | `EXACT-DEP-RESET` | 0.019 | 0.030 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:voideditor__void.17e7a5b1:root:6522748bd07c0bd9` | `EXACT-DEP-ATTACH` | 1.428 | 1.434 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:voideditor__void.17e7a5b1:root:6522748bd07c0bd9` | `EXACT-DEP-MATERIALIZE` | 10424.352 | 10565.325 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:voideditor__void.17e7a5b1:root:6522748bd07c0bd9` | `EXACT-DEP-RESET` | 0.021 | 0.028 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:webpack__webpack.24e3c2d2:root:2a4de1074e7ce9a8` | `EXACT-DEP-ATTACH` | 1.127 | 1.579 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:webpack__webpack.24e3c2d2:root:2a4de1074e7ce9a8` | `EXACT-DEP-MATERIALIZE` | 7182.893 | 7255.131 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `dependency_view:webpack__webpack.24e3c2d2:root:2a4de1074e7ce9a8` | `EXACT-DEP-RESET` | 0.019 | 0.021 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `native_binary_bundle:NativeScript__NativeScript.3d6a4392:root:@swc_core:115` | `EXACT-NATIVE-LOAD` | 25.732 | 62.374 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `native_binary_bundle:nightwatchjs__nightwatch.54c8550c:root:@swc_core:109` | `EXACT-NATIVE-LOAD` | 85.539 | 88.570 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `native_binary_bundle:payloadcms__payload.8f660355:root:@swc_core:115` | `EXACT-NATIVE-LOAD` | 25.311 | 25.853 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `native_binary_bundle:payloadcms__payload.8f660355:root:node-gyp:115` | `EXACT-NATIVE-LOAD` | 24.594 | 155.129 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `native_binary_bundle:webpack__webpack.24e3c2d2:root:node-gyp:115` | `EXACT-NATIVE-LOAD` | 24.517 | 26.151 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:Automattic__mongoose:5f57a5bbb2e8dfed8d04be47cdd17728633c44c1` | `EXACT-REPO-ATTACH` | 0.028 | 0.033 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:Automattic__mongoose:5f57a5bbb2e8dfed8d04be47cdd17728633c44c1` | `EXACT-REPO-MATERIALIZE` | 16.121 | 16.343 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:Effect-TS__effect:5df4da10de444f379a166f4b28721e75100bb838` | `EXACT-REPO-ATTACH` | 0.031 | 0.036 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:Effect-TS__effect:5df4da10de444f379a166f4b28721e75100bb838` | `EXACT-REPO-MATERIALIZE` | 52.464 | 56.132 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:FuelLabs__fuels-ts:b3f37c91aca4aa9d5e4c0d3967f66237190826ea` | `EXACT-REPO-ATTACH` | 0.040 | 51.952 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:FuelLabs__fuels-ts:b3f37c91aca4aa9d5e4c0d3967f66237190826ea` | `EXACT-REPO-MATERIALIZE` | 49.796 | 52.120 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:GitbookIO__gitbook:81f8ddcf27ec398a33b6f676a81e9a791b673ce2` | `EXACT-REPO-ATTACH` | 0.024 | 0.030 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:GitbookIO__gitbook:81f8ddcf27ec398a33b6f676a81e9a791b673ce2` | `EXACT-REPO-MATERIALIZE` | 20.551 | 20.991 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:NativeScript__NativeScript:3d6a4392f6008e4f43f8f5439a256c50e3707101` | `EXACT-REPO-ATTACH` | 0.128 | 68.100 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:NativeScript__NativeScript:3d6a4392f6008e4f43f8f5439a256c50e3707101` | `EXACT-REPO-MATERIALIZE` | 150.762 | 154.795 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:Netflix__falcor:39d64776cf9d87781b2791615dcbae73b2bcd2e1` | `EXACT-REPO-ATTACH` | 0.028 | 0.030 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:Netflix__falcor:39d64776cf9d87781b2791615dcbae73b2bcd2e1` | `EXACT-REPO-MATERIALIZE` | 11.871 | 12.042 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:OpenCut-app__OpenCut:e84c0cfda6784abb9bcb72aae757233cd8951780` | `EXACT-REPO-ATTACH` | 0.026 | 0.032 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:OpenCut-app__OpenCut:e84c0cfda6784abb9bcb72aae757233cd8951780` | `EXACT-REPO-MATERIALIZE` | 28.248 | 29.151 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:ReactiveX__rxjs:c15b37f81ba5f5abea8c872b0189a70b150df4cb` | `EXACT-REPO-ATTACH` | 0.027 | 0.029 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:ReactiveX__rxjs:c15b37f81ba5f5abea8c872b0189a70b150df4cb` | `EXACT-REPO-MATERIALIZE` | 26.571 | 27.025 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:Redocly__redoc:d41fd46f7cbee86bf83dc17b7ec51baf54f72a54` | `EXACT-REPO-ATTACH` | 0.031 | 74.127 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:Redocly__redoc:d41fd46f7cbee86bf83dc17b7ec51baf54f72a54` | `EXACT-REPO-MATERIALIZE` | 10.152 | 10.346 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:Shopify__draggable:8a1eed57f3ab2dff9371e8ce60fb39ac85871e8d` | `EXACT-REPO-ATTACH` | 0.032 | 0.037 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:Shopify__draggable:8a1eed57f3ab2dff9371e8ce60fb39ac85871e8d` | `EXACT-REPO-MATERIALIZE` | 9.968 | 10.463 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:advplyr__audiobookshelf:626596b192013ba9f5a011dd110e288124c95ebe` | `EXACT-REPO-ATTACH` | 0.034 | 37.221 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:advplyr__audiobookshelf:626596b192013ba9f5a011dd110e288124c95ebe` | `EXACT-REPO-MATERIALIZE` | 28.154 | 28.533 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:ajayyy__SponsorBlock:dfddffbc5128dbc55b4dc7c83cdcd18787f48ba4` | `EXACT-REPO-ATTACH` | 0.027 | 0.028 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:ajayyy__SponsorBlock:dfddffbc5128dbc55b4dc7c83cdcd18787f48ba4` | `EXACT-REPO-MATERIALIZE` | 6.377 | 6.548 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:antvis__G6:91c0ac85e4e636a05bd1a3c5e56a4928d1242a9b` | `EXACT-REPO-ATTACH` | 0.058 | 77.300 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:antvis__G6:91c0ac85e4e636a05bd1a3c5e56a4928d1242a9b` | `EXACT-REPO-MATERIALIZE` | 43.604 | 45.965 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:axios__axios:ef36347fb559383b04c755b07f1a8d11897fab7f` | `EXACT-REPO-ATTACH` | 0.030 | 5.873 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:axios__axios:ef36347fb559383b04c755b07f1a8d11897fab7f` | `EXACT-REPO-MATERIALIZE` | 9.213 | 9.364 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:babel__babel:2ea3fc8f9b33a911840f17fbc407e7bfae2ed66f` | `EXACT-REPO-ATTACH` | 54.936 | 154.610 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:babel__babel:2ea3fc8f9b33a911840f17fbc407e7bfae2ed66f` | `EXACT-REPO-MATERIALIZE` | 878.301 | 1017.141 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:balderdashy__sails:ffebacc58c27f878c9373702bc3a3f91a02bca0c` | `EXACT-REPO-ATTACH` | 0.027 | 0.038 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:balderdashy__sails:ffebacc58c27f878c9373702bc3a3f91a02bca0c` | `EXACT-REPO-MATERIALIZE` | 14.615 | 15.214 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:bluesky-social__social-app:cbd48c855a57f1a294f4b7362eaadb505bf5f9f6` | `EXACT-REPO-ATTACH` | 0.039 | 137.373 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:bluesky-social__social-app:cbd48c855a57f1a294f4b7362eaadb505bf5f9f6` | `EXACT-REPO-MATERIALIZE` | 89.627 | 93.807 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:bootstrap-vue__bootstrap-vue:9a246f45fc813f161df291fc7d6197febf8afaf4` | `EXACT-REPO-ATTACH` | 0.034 | 12.972 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:bootstrap-vue__bootstrap-vue:9a246f45fc813f161df291fc7d6197febf8afaf4` | `EXACT-REPO-MATERIALIZE` | 21.382 | 21.994 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:bpampuch__pdfmake:719e73140cce75a792f7f419c27fc33a230e73d2` | `EXACT-REPO-ATTACH` | 0.026 | 0.028 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:bpampuch__pdfmake:719e73140cce75a792f7f419c27fc33a230e73d2` | `EXACT-REPO-MATERIALIZE` | 16.998 | 17.268 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:brianc__node-postgres:ecff60dc8aa0bd1ad5ea8f4623af0756a86dc110` | `EXACT-REPO-ATTACH` | 0.026 | 2.946 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:brianc__node-postgres:ecff60dc8aa0bd1ad5ea8f4623af0756a86dc110` | `EXACT-REPO-MATERIALIZE` | 8.196 | 8.295 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:caolan__async:23dbf76aeb04c7c3dd56276115b277e3fa9dd5cc` | `EXACT-REPO-ATTACH` | 0.030 | 0.064 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:caolan__async:23dbf76aeb04c7c3dd56276115b277e3fa9dd5cc` | `EXACT-REPO-MATERIALIZE` | 16.804 | 17.079 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:coder__code-server:e90504b8cf1d73c36d902bbaaec7bab33f15c42e` | `EXACT-REPO-ATTACH` | 0.031 | 0.067 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:coder__code-server:e90504b8cf1d73c36d902bbaaec7bab33f15c42e` | `EXACT-REPO-MATERIALIZE` | 7.482 | 7.597 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:directus__directus:ac922d18f6039582a18737a6dc6d1d9a08a194e8` | `EXACT-REPO-ATTACH` | 0.048 | 48.078 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:directus__directus:ac922d18f6039582a18737a6dc6d1d9a08a194e8` | `EXACT-REPO-MATERIALIZE` | 63.413 | 78.452 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:emotion-js__emotion:b882bcba85132554992e4bd49e94c95939bbf810` | `EXACT-REPO-ATTACH` | 0.034 | 0.037 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:emotion-js__emotion:b882bcba85132554992e4bd49e94c95939bbf810` | `EXACT-REPO-MATERIALIZE` | 19.461 | 19.920 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:enzymejs__enzyme:61e1b47c4bdc4509b2ac286c0d3ae3df172d26f0` | `EXACT-REPO-ATTACH` | 0.031 | 11.035 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:enzymejs__enzyme:61e1b47c4bdc4509b2ac286c0d3ae3df172d26f0` | `EXACT-REPO-MATERIALIZE` | 8.653 | 9.330 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:fabricjs__fabric.js:6742471c23e5fd8afbb1282246b4b785455c8c17` | `EXACT-REPO-ATTACH` | 0.035 | 0.070 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:fabricjs__fabric.js:6742471c23e5fd8afbb1282246b4b785455c8c17` | `EXACT-REPO-MATERIALIZE` | 44.701 | 45.489 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:foambubble__foam:2cac816272157f3a964b30adf4f29c0b2973cce8` | `EXACT-REPO-ATTACH` | 0.027 | 0.048 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:foambubble__foam:2cac816272157f3a964b30adf4f29c0b2973cce8` | `EXACT-REPO-MATERIALIZE` | 50.935 | 51.985 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:foliojs__pdfkit:d0108157f13d763ad5287a2293436b5a1aecf055` | `EXACT-REPO-ATTACH` | 0.027 | 0.030 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:foliojs__pdfkit:d0108157f13d763ad5287a2293436b5a1aecf055` | `EXACT-REPO-MATERIALIZE` | 28.129 | 28.860 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:homebridge__homebridge:3a341e0838c99abfdf7a2d76e5e1e2a2af7ccb09` | `EXACT-REPO-ATTACH` | 0.026 | 0.040 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:homebridge__homebridge:3a341e0838c99abfdf7a2d76e5e1e2a2af7ccb09` | `EXACT-REPO-MATERIALIZE` | 4.090 | 4.114 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:humanlayer__12-factor-agents:d20c728368bf9c189d6d7aab704744decb6ec0cc` | `EXACT-REPO-ATTACH` | 0.026 | 0.047 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:humanlayer__12-factor-agents:d20c728368bf9c189d6d7aab704744decb6ec0cc` | `EXACT-REPO-MATERIALIZE` | 38.383 | 38.637 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:iamkun__dayjs:c8a26460d89a2ee9a7d3b9cafa124ea856ee883f` | `EXACT-REPO-ATTACH` | 0.037 | 18.140 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:iamkun__dayjs:c8a26460d89a2ee9a7d3b9cafa124ea856ee883f` | `EXACT-REPO-MATERIALIZE` | 8.673 | 9.767 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:jantimon__html-webpack-plugin:9a39db807c09d8e6145e5047cfe2ec5e928e1dee` | `EXACT-REPO-ATTACH` | 0.029 | 0.031 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:jantimon__html-webpack-plugin:9a39db807c09d8e6145e5047cfe2ec5e928e1dee` | `EXACT-REPO-MATERIALIZE` | 7.165 | 7.479 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:jaredpalmer__formik:91475adbf33579561e580eceea0c031f4ec2e992` | `EXACT-REPO-ATTACH` | 0.033 | 0.039 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:jaredpalmer__formik:91475adbf33579561e580eceea0c031f4ec2e992` | `EXACT-REPO-MATERIALIZE` | 11.751 | 11.853 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:josdejong__jsoneditor:0319b2131df47f1220d74e3ff174d5c02973ec7d` | `EXACT-REPO-ATTACH` | 0.031 | 13.982 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:josdejong__jsoneditor:0319b2131df47f1220d74e3ff174d5c02973ec7d` | `EXACT-REPO-MATERIALIZE` | 5.978 | 6.082 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:josdejong__mathjs:04e6e2d7a949d6ddc7d7139bf1e3a88e6fe5365b` | `EXACT-REPO-ATTACH` | 0.031 | 15.759 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:josdejong__mathjs:04e6e2d7a949d6ddc7d7139bf1e3a88e6fe5365b` | `EXACT-REPO-MATERIALIZE` | 22.246 | 23.703 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:marko-js__marko:24b9402cd54c3a74f200da0f79dd19350995a9ba` | `EXACT-REPO-ATTACH` | 0.969 | 11.477 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:marko-js__marko:24b9402cd54c3a74f200da0f79dd19350995a9ba` | `EXACT-REPO-MATERIALIZE` | 198.031 | 238.171 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:marmelab__react-admin:823caa0b6489fc8133685525e22d30ddf57643fa` | `EXACT-REPO-ATTACH` | 0.036 | 0.038 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:marmelab__react-admin:823caa0b6489fc8133685525e22d30ddf57643fa` | `EXACT-REPO-MATERIALIZE` | 154.615 | 159.175 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:mholt__PapaParse:b10b87ef8686c6f88299b50dd25e83606e9c36d4` | `EXACT-REPO-ATTACH` | 0.026 | 0.029 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:mholt__PapaParse:b10b87ef8686c6f88299b50dd25e83606e9c36d4` | `EXACT-REPO-MATERIALIZE` | 33.508 | 34.811 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:microsoft__vscode:4166e90ac290db7f77800a4f6702903ea4eed476` | `EXACT-REPO-ATTACH` | 11.995 | 45.628 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:microsoft__vscode:4166e90ac290db7f77800a4f6702903ea4eed476` | `EXACT-REPO-MATERIALIZE` | 219.999 | 228.753 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:mochajs__mocha:410ce0d2a0f799aaca2c0bc627294d70c62dd3f4` | `EXACT-REPO-ATTACH` | 0.039 | 0.047 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:mochajs__mocha:410ce0d2a0f799aaca2c0bc627294d70c62dd3f4` | `EXACT-REPO-MATERIALIZE` | 14.945 | 15.809 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:necolas__react-native-web:a9de220ba9e65bdea540fb5322ffb1da2b0bf442` | `EXACT-REPO-ATTACH` | 0.026 | 72.943 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:necolas__react-native-web:a9de220ba9e65bdea540fb5322ffb1da2b0bf442` | `EXACT-REPO-MATERIALIZE` | 14.777 | 15.426 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:nestjs__nest:346c9543120c692f314bdbf55fc9956d2fa6d87e` | `EXACT-REPO-ATTACH` | 9.331 | 31.257 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:nestjs__nest:346c9543120c692f314bdbf55fc9956d2fa6d87e` | `EXACT-REPO-MATERIALIZE` | 36.975 | 37.413 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:nightwatchjs__nightwatch:54c8550c75a16c61827c0bad043c7ffa073a52e6` | `EXACT-REPO-ATTACH` | 2.011 | 4.143 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:nightwatchjs__nightwatch:54c8550c75a16c61827c0bad043c7ffa073a52e6` | `EXACT-REPO-MATERIALIZE` | 22.361 | 23.379 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:nock__nock:e7418da29feb4a7bf0aa1612bfb9d32a4051651e` | `EXACT-REPO-ATTACH` | 0.031 | 5.939 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:nock__nock:e7418da29feb4a7bf0aa1612bfb9d32a4051651e` | `EXACT-REPO-MATERIALIZE` | 5.270 | 5.480 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:novnc__noVNC:d44f7e04fc456844836c7c5ac911d0f4e8dd06e6` | `EXACT-REPO-ATTACH` | 0.029 | 5.987 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:novnc__noVNC:d44f7e04fc456844836c7c5ac911d0f4e8dd06e6` | `EXACT-REPO-MATERIALIZE` | 7.699 | 7.892 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:payloadcms__payload:8f66035522f568d42098a7ad525e7bf700662b9a` | `EXACT-REPO-ATTACH` | 0.051 | 45.297 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:payloadcms__payload:8f66035522f568d42098a7ad525e7bf700662b9a` | `EXACT-REPO-MATERIALIZE` | 185.498 | 320.969 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:react-hook-form__react-hook-form:3adba2b816dd50bbca460bbe61df64b50bc6b1da` | `EXACT-REPO-ATTACH` | 0.032 | 0.035 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:react-hook-form__react-hook-form:3adba2b816dd50bbca460bbe61df64b50bc6b1da` | `EXACT-REPO-MATERIALIZE` | 12.234 | 12.509 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:reactjs__react-transition-group:2989b5b87b4b4d1001f21c8efa503049ffb4fe8d` | `EXACT-REPO-ATTACH` | 0.025 | 70.155 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:reactjs__react-transition-group:2989b5b87b4b4d1001f21c8efa503049ffb4fe8d` | `EXACT-REPO-MATERIALIZE` | 4.001 | 4.148 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:redux-saga__redux-saga:a4ace10dc3ff182828cd3ee7469f6667e08ceb62` | `EXACT-REPO-ATTACH` | 0.033 | 0.037 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:redux-saga__redux-saga:a4ace10dc3ff182828cd3ee7469f6667e08ceb62` | `EXACT-REPO-MATERIALIZE` | 10.306 | 10.536 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:refined-github__refined-github:d4a7c3fbfebff5f39a3760effbea7273dea0d01c` | `EXACT-REPO-ATTACH` | 0.029 | 0.036 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:refined-github__refined-github:d4a7c3fbfebff5f39a3760effbea7273dea0d01c` | `EXACT-REPO-MATERIALIZE` | 11.026 | 11.130 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:remy__nodemon:daad5c162919fa6abff53be16832bdf55f2204ad` | `EXACT-REPO-ATTACH` | 0.029 | 0.038 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:remy__nodemon:daad5c162919fa6abff53be16832bdf55f2204ad` | `EXACT-REPO-MATERIALIZE` | 10.417 | 10.539 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:segmentio__evergreen:9b774aee2d794f6cf2f73a054bd33066ca5898a9` | `EXACT-REPO-ATTACH` | 0.031 | 0.052 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:segmentio__evergreen:9b774aee2d794f6cf2f73a054bd33066ca5898a9` | `EXACT-REPO-MATERIALIZE` | 28.665 | 31.356 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:strapi__strapi:e5b87a54008c9de2b3286a4774635dcf69895d9b` | `EXACT-REPO-ATTACH` | 36.201 | 96.111 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:strapi__strapi:e5b87a54008c9de2b3286a4774635dcf69895d9b` | `EXACT-REPO-MATERIALIZE` | 131.580 | 168.147 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:sveltejs__svelte:6c9717a91f2f6ae10641d1cf502ba13d227fbe45` | `EXACT-REPO-ATTACH` | 0.032 | 5.408 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:sveltejs__svelte:6c9717a91f2f6ae10641d1cf502ba13d227fbe45` | `EXACT-REPO-MATERIALIZE` | 157.196 | 305.181 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:svg__svgo:c06d8f6899788defae9594537063c2f4307803e4` | `EXACT-REPO-ATTACH` | 0.027 | 0.035 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:svg__svgo:c06d8f6899788defae9594537063c2f4307803e4` | `EXACT-REPO-MATERIALIZE` | 12.831 | 13.097 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:tinacms__tinacms:dffb104f1850cabc15f495a5868a33a66295965a` | `EXACT-REPO-ATTACH` | 3.008 | 286.359 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:tinacms__tinacms:dffb104f1850cabc15f495a5868a33a66295965a` | `EXACT-REPO-MATERIALIZE` | 47.503 | 49.041 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:trpc__trpc:2f40ba935ad7f7d29eec3f9c45d353450b43e852` | `EXACT-REPO-ATTACH` | 0.031 | 133.675 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:trpc__trpc:2f40ba935ad7f7d29eec3f9c45d353450b43e852` | `EXACT-REPO-MATERIALIZE` | 27.213 | 28.573 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:ueberdosis__tiptap:2d6de06c34c239e78fedd6bd2a0bcea42d0fdbfa` | `EXACT-REPO-ATTACH` | 0.032 | 86.957 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:ueberdosis__tiptap:2d6de06c34c239e78fedd6bd2a0bcea42d0fdbfa` | `EXACT-REPO-MATERIALIZE` | 42.351 | 44.517 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:umijs__qiankun:693cdde75049830820ff9490dd267f9701db25e6` | `EXACT-REPO-ATTACH` | 0.027 | 0.705 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:umijs__qiankun:693cdde75049830820ff9490dd267f9701db25e6` | `EXACT-REPO-MATERIALIZE` | 10.567 | 10.656 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:vitejs__vite:8b47ff76d28630b4dc39c77fbd2762b4c36ad23d` | `EXACT-REPO-ATTACH` | 0.032 | 55.105 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:vitejs__vite:8b47ff76d28630b4dc39c77fbd2762b4c36ad23d` | `EXACT-REPO-MATERIALIZE` | 58.225 | 81.559 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:voideditor__void:17e7a5b1524345b19ab4ee38ec4f9b1b75a1bd00` | `EXACT-REPO-ATTACH` | 8.615 | 89.430 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:voideditor__void:17e7a5b1524345b19ab4ee38ec4f9b1b75a1bd00` | `EXACT-REPO-MATERIALIZE` | 220.090 | 277.346 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:webpack__webpack:24e3c2d2c9f8c6d60810302b2ea70ed86e2863dc` | `EXACT-REPO-ATTACH` | 10.501 | 61.145 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:webpack__webpack:24e3c2d2c9f8c6d60810302b2ea70ed86e2863dc` | `EXACT-REPO-MATERIALIZE` | 182.774 | 267.343 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:websockets__ws:726c3732b3e5319219ed73cac4826fd36917e2e1` | `EXACT-REPO-ATTACH` | 0.027 | 62.963 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:websockets__ws:726c3732b3e5319219ed73cac4826fd36917e2e1` | `EXACT-REPO-MATERIALIZE` | 3.568 | 3.701 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:welldone-software__why-did-you-render:3ec3512d750c49448fe2241e26d05db9e42f0c21` | `EXACT-REPO-ATTACH` | 0.028 | 0.029 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `repo_baseline:welldone-software__why-did-you-render:3ec3512d750c49448fe2241e26d05db9e42f0c21` | `EXACT-REPO-MATERIALIZE` | 5.629 | 5.811 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_18` | `EXACT-ROOTFS-ATTACH` | 11.901 | 12.420 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_18` | `EXACT-ROOTFS-CREATE` | 58.390 | 91.762 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_18` | `EXACT-ROOTFS-RESET` | 21.711 | 400.786 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_18-bullseye` | `EXACT-ROOTFS-ATTACH` | 11.385 | 11.902 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_18-bullseye` | `EXACT-ROOTFS-CREATE` | 44.268 | 194.379 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_18-bullseye` | `EXACT-ROOTFS-RESET` | 20.107 | 108.664 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_18-bullseye-slim` | `EXACT-ROOTFS-ATTACH` | 11.386 | 11.646 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_18-bullseye-slim` | `EXACT-ROOTFS-CREATE` | 43.311 | 45.960 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_18-bullseye-slim` | `EXACT-ROOTFS-RESET` | 20.252 | 21.541 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_18-slim` | `EXACT-ROOTFS-ATTACH` | 11.158 | 11.353 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_18-slim` | `EXACT-ROOTFS-CREATE` | 45.599 | 52.834 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_18-slim` | `EXACT-ROOTFS-RESET` | 20.611 | 21.418 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_20` | `EXACT-ROOTFS-ATTACH` | 11.268 | 11.522 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_20` | `EXACT-ROOTFS-CREATE` | 44.606 | 51.717 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_20` | `EXACT-ROOTFS-RESET` | 20.682 | 23.290 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_20-bookworm` | `EXACT-ROOTFS-ATTACH` | 10.986 | 11.142 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_20-bookworm` | `EXACT-ROOTFS-CREATE` | 45.936 | 53.161 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_20-bookworm` | `EXACT-ROOTFS-RESET` | 20.130 | 22.816 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_20-bullseye` | `EXACT-ROOTFS-ATTACH` | 10.998 | 11.275 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_20-bullseye` | `EXACT-ROOTFS-CREATE` | 44.566 | 50.245 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_20-bullseye` | `EXACT-ROOTFS-RESET` | 23.286 | 24.772 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_20-bullseye-slim` | `EXACT-ROOTFS-ATTACH` | 11.451 | 11.897 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_20-bullseye-slim` | `EXACT-ROOTFS-CREATE` | 42.637 | 46.163 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_20-bullseye-slim` | `EXACT-ROOTFS-RESET` | 21.002 | 21.970 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_20-slim` | `EXACT-ROOTFS-ATTACH` | 11.512 | 12.265 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_20-slim` | `EXACT-ROOTFS-CREATE` | 47.126 | 50.811 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_20-slim` | `EXACT-ROOTFS-RESET` | 20.723 | 21.232 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_22` | `EXACT-ROOTFS-ATTACH` | 11.161 | 11.600 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_22` | `EXACT-ROOTFS-CREATE` | 43.172 | 47.010 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_22` | `EXACT-ROOTFS-RESET` | 20.478 | 23.719 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_22-bookworm` | `EXACT-ROOTFS-ATTACH` | 11.496 | 11.979 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_22-bookworm` | `EXACT-ROOTFS-CREATE` | 42.158 | 44.904 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_22-bookworm` | `EXACT-ROOTFS-RESET` | 20.048 | 21.428 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_22-bookworm-slim` | `EXACT-ROOTFS-ATTACH` | 11.203 | 11.729 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_22-bookworm-slim` | `EXACT-ROOTFS-CREATE` | 46.950 | 48.794 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_22-bookworm-slim` | `EXACT-ROOTFS-RESET` | 20.407 | 23.927 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_22-bullseye-slim` | `EXACT-ROOTFS-ATTACH` | 11.688 | 11.864 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_22-bullseye-slim` | `EXACT-ROOTFS-CREATE` | 44.046 | 107.234 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_22-bullseye-slim` | `EXACT-ROOTFS-RESET` | 20.692 | 26.788 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_22-slim` | `EXACT-ROOTFS-ATTACH` | 11.530 | 11.706 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_22-slim` | `EXACT-ROOTFS-CREATE` | 43.851 | 45.567 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `rootfs:node_22-slim` | `EXACT-ROOTFS-RESET` | 21.682 | 24.263 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:Automattic__mongoose.5f57a5bb:root` | `EXACT-SOURCE-MATERIALIZE` | 18.731 | 19.789 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:Automattic__mongoose.5f57a5bb:root` | `EXACT-SOURCE-RESET` | 3.751 | 3.787 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:Effect-TS__effect.5df4da10:root` | `EXACT-SOURCE-MATERIALIZE` | 50.541 | 55.728 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:Effect-TS__effect.5df4da10:root` | `EXACT-SOURCE-RESET` | 23.603 | 23.793 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:FuelLabs__fuels-ts.b3f37c91:root` | `EXACT-SOURCE-MATERIALIZE` | 52.273 | 54.900 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:FuelLabs__fuels-ts.b3f37c91:root` | `EXACT-SOURCE-RESET` | 27.275 | 28.008 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:GitbookIO__gitbook.81f8ddcf:root` | `EXACT-SOURCE-MATERIALIZE` | 25.621 | 26.269 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:GitbookIO__gitbook.81f8ddcf:root` | `EXACT-SOURCE-RESET` | 5.632 | 5.657 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:NativeScript__NativeScript.3d6a4392:root` | `EXACT-SOURCE-MATERIALIZE` | 127.444 | 130.648 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:NativeScript__NativeScript.3d6a4392:root` | `EXACT-SOURCE-RESET` | 45.422 | 47.893 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:Netflix__falcor.39d64776:root` | `EXACT-SOURCE-MATERIALIZE` | 10.819 | 11.366 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:Netflix__falcor.39d64776:root` | `EXACT-SOURCE-RESET` | 4.375 | 4.816 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:OpenCut-app__OpenCut.e84c0cfd:root` | `EXACT-SOURCE-MATERIALIZE` | 23.820 | 24.429 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:OpenCut-app__OpenCut.e84c0cfd:root` | `EXACT-SOURCE-RESET` | 2.739 | 2.788 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:ReactiveX__rxjs.c15b37f8:root` | `EXACT-SOURCE-MATERIALIZE` | 27.624 | 30.487 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:ReactiveX__rxjs.c15b37f8:root` | `EXACT-SOURCE-RESET` | 11.241 | 13.442 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:Redocly__redoc.d41fd46f:root` | `EXACT-SOURCE-MATERIALIZE` | 11.201 | 11.419 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:Redocly__redoc.d41fd46f:root` | `EXACT-SOURCE-RESET` | 2.096 | 2.130 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:Shopify__draggable.8a1eed57:root` | `EXACT-SOURCE-MATERIALIZE` | 11.147 | 11.806 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:Shopify__draggable.8a1eed57:root` | `EXACT-SOURCE-RESET` | 2.830 | 4.598 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:advplyr__audiobookshelf.626596b1:client` | `EXACT-SOURCE-MATERIALIZE` | 26.310 | 28.132 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:advplyr__audiobookshelf.626596b1:client` | `EXACT-SOURCE-RESET` | 11.855 | 12.310 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:advplyr__audiobookshelf.626596b1:root` | `EXACT-SOURCE-MATERIALIZE` | 25.075 | 27.563 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:advplyr__audiobookshelf.626596b1:root` | `EXACT-SOURCE-RESET` | 11.318 | 128.561 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:ajayyy__SponsorBlock.dfddffbc:root` | `EXACT-SOURCE-MATERIALIZE` | 7.000 | 7.149 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:ajayyy__SponsorBlock.dfddffbc:root` | `EXACT-SOURCE-RESET` | 1.178 | 1.476 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:antvis__G6.91c0ac85:root` | `EXACT-SOURCE-MATERIALIZE` | 49.623 | 51.710 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:antvis__G6.91c0ac85:root` | `EXACT-SOURCE-RESET` | 23.460 | 59.075 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:axios__axios.ef36347f:root` | `EXACT-SOURCE-MATERIALIZE` | 8.853 | 9.502 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:axios__axios.ef36347f:root` | `EXACT-SOURCE-RESET` | 3.293 | 3.620 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:babel__babel.2ea3fc8f:root` | `EXACT-SOURCE-MATERIALIZE` | 1049.110 | 1241.777 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:babel__babel.2ea3fc8f:root` | `EXACT-SOURCE-RESET` | 532.345 | 539.250 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:balderdashy__sails.ffebacc5:root` | `EXACT-SOURCE-MATERIALIZE` | 18.600 | 18.861 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:balderdashy__sails.ffebacc5:root` | `EXACT-SOURCE-RESET` | 4.520 | 4.728 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:bluesky-social__social-app.cbd48c85:root` | `EXACT-SOURCE-MATERIALIZE` | 79.557 | 82.468 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:bluesky-social__social-app.cbd48c85:root` | `EXACT-SOURCE-RESET` | 33.014 | 35.139 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:bootstrap-vue__bootstrap-vue.9a246f45:root` | `EXACT-SOURCE-MATERIALIZE` | 25.354 | 25.833 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:bootstrap-vue__bootstrap-vue.9a246f45:root` | `EXACT-SOURCE-RESET` | 4.682 | 7.355 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:bpampuch__pdfmake.719e7314:root` | `EXACT-SOURCE-MATERIALIZE` | 14.714 | 14.884 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:bpampuch__pdfmake.719e7314:root` | `EXACT-SOURCE-RESET` | 1.117 | 1.132 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:brianc__node-postgres.ecff60dc:root` | `EXACT-SOURCE-MATERIALIZE` | 9.963 | 9.992 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:brianc__node-postgres.ecff60dc:root` | `EXACT-SOURCE-RESET` | 2.158 | 2.211 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:caolan__async.23dbf76a:root` | `EXACT-SOURCE-MATERIALIZE` | 16.554 | 17.792 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:caolan__async.23dbf76a:root` | `EXACT-SOURCE-RESET` | 3.481 | 5.990 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:coder__code-server.e90504b8:root` | `EXACT-SOURCE-MATERIALIZE` | 8.299 | 8.632 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:coder__code-server.e90504b8:root` | `EXACT-SOURCE-RESET` | 1.553 | 1.627 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:directus__directus.ac922d18:root` | `EXACT-SOURCE-MATERIALIZE` | 78.012 | 84.949 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:directus__directus.ac922d18:root` | `EXACT-SOURCE-RESET` | 41.440 | 58.762 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:emotion-js__emotion.b882bcba:root` | `EXACT-SOURCE-MATERIALIZE` | 23.545 | 24.080 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:emotion-js__emotion.b882bcba:root` | `EXACT-SOURCE-RESET` | 5.387 | 5.417 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:enzymejs__enzyme.61e1b47c:root` | `EXACT-SOURCE-MATERIALIZE` | 10.203 | 10.341 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:enzymejs__enzyme.61e1b47c:root` | `EXACT-SOURCE-RESET` | 2.194 | 59.322 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:fabricjs__fabric.js.6742471c:root` | `EXACT-SOURCE-MATERIALIZE` | 39.643 | 44.823 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:fabricjs__fabric.js.6742471c:root` | `EXACT-SOURCE-RESET` | 14.025 | 15.127 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:foambubble__foam.2cac8162:root` | `EXACT-SOURCE-MATERIALIZE` | 38.793 | 41.194 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:foambubble__foam.2cac8162:root` | `EXACT-SOURCE-RESET` | 2.538 | 2.554 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:foliojs__pdfkit.d0108157:root` | `EXACT-SOURCE-MATERIALIZE` | 24.397 | 25.191 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:foliojs__pdfkit.d0108157:root` | `EXACT-SOURCE-RESET` | 1.747 | 1.841 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:homebridge__homebridge.3a341e08:root` | `EXACT-SOURCE-MATERIALIZE` | 4.190 | 4.309 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:homebridge__homebridge.3a341e08:root` | `EXACT-SOURCE-RESET` | 0.553 | 0.632 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:humanlayer__12-factor-agents.d20c7283:packages_walkthroughgen` | `EXACT-SOURCE-MATERIALIZE` | 33.662 | 34.091 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:humanlayer__12-factor-agents.d20c7283:packages_walkthroughgen` | `EXACT-SOURCE-RESET` | 3.068 | 3.107 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:iamkun__dayjs.c8a26460:root` | `EXACT-SOURCE-MATERIALIZE` | 9.940 | 12.524 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:iamkun__dayjs.c8a26460:root` | `EXACT-SOURCE-RESET` | 4.396 | 5.333 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:jantimon__html-webpack-plugin.9a39db80:root` | `EXACT-SOURCE-MATERIALIZE` | 7.682 | 7.793 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:jantimon__html-webpack-plugin.9a39db80:root` | `EXACT-SOURCE-RESET` | 1.402 | 1.419 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:jaredpalmer__formik.91475adb:root` | `EXACT-SOURCE-MATERIALIZE` | 12.029 | 12.069 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:jaredpalmer__formik.91475adb:root` | `EXACT-SOURCE-RESET` | 1.996 | 2.032 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:josdejong__jsoneditor.0319b213:root` | `EXACT-SOURCE-MATERIALIZE` | 6.172 | 6.335 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:josdejong__jsoneditor.0319b213:root` | `EXACT-SOURCE-RESET` | 1.014 | 1.041 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:josdejong__mathjs.04e6e2d7:root` | `EXACT-SOURCE-MATERIALIZE` | 24.459 | 30.537 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:josdejong__mathjs.04e6e2d7:root` | `EXACT-SOURCE-RESET` | 11.947 | 12.317 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:marko-js__marko.24b9402c:root` | `EXACT-SOURCE-MATERIALIZE` | 266.727 | 289.008 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:marko-js__marko.24b9402c:root` | `EXACT-SOURCE-RESET` | 146.944 | 150.239 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:marmelab__react-admin.823caa0b:root` | `EXACT-SOURCE-MATERIALIZE` | 121.885 | 125.108 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:marmelab__react-admin.823caa0b:root` | `EXACT-SOURCE-RESET` | 43.707 | 46.567 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:mholt__PapaParse.b10b87ef:root` | `EXACT-SOURCE-MATERIALIZE` | 23.710 | 24.901 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:mholt__PapaParse.b10b87ef:root` | `EXACT-SOURCE-RESET` | 0.337 | 0.350 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:microsoft__vscode.4166e90a:root` | `EXACT-SOURCE-MATERIALIZE` | 248.589 | 252.279 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:microsoft__vscode.4166e90a:root` | `EXACT-SOURCE-RESET` | 127.788 | 130.771 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:mochajs__mocha.410ce0d2:root` | `EXACT-SOURCE-MATERIALIZE` | 18.974 | 19.384 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:mochajs__mocha.410ce0d2:root` | `EXACT-SOURCE-RESET` | 4.008 | 4.373 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:necolas__react-native-web.a9de220b:root` | `EXACT-SOURCE-MATERIALIZE` | 16.608 | 17.564 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:necolas__react-native-web.a9de220b:root` | `EXACT-SOURCE-RESET` | 6.894 | 7.966 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:nestjs__nest.346c9543:root` | `EXACT-SOURCE-MATERIALIZE` | 47.376 | 48.268 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:nestjs__nest.346c9543:root` | `EXACT-SOURCE-RESET` | 24.851 | 26.169 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:nightwatchjs__nightwatch.54c8550c:root` | `EXACT-SOURCE-MATERIALIZE` | 26.551 | 28.242 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:nightwatchjs__nightwatch.54c8550c:root` | `EXACT-SOURCE-RESET` | 13.524 | 13.652 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:nock__nock.e7418da2:root` | `EXACT-SOURCE-MATERIALIZE` | 5.534 | 5.619 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:nock__nock.e7418da2:root` | `EXACT-SOURCE-RESET` | 0.742 | 0.767 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:novnc__noVNC.d44f7e04:root` | `EXACT-SOURCE-MATERIALIZE` | 7.914 | 8.122 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:novnc__noVNC.d44f7e04:root` | `EXACT-SOURCE-RESET` | 1.184 | 1.517 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:payloadcms__payload.8f660355:root` | `EXACT-SOURCE-MATERIALIZE` | 205.874 | 208.025 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:payloadcms__payload.8f660355:root` | `EXACT-SOURCE-RESET` | 111.449 | 113.310 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:react-hook-form__react-hook-form.3adba2b8:root` | `EXACT-SOURCE-MATERIALIZE` | 13.869 | 13.969 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:react-hook-form__react-hook-form.3adba2b8:root` | `EXACT-SOURCE-RESET` | 2.579 | 57.498 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:reactjs__react-transition-group.2989b5b8:root` | `EXACT-SOURCE-MATERIALIZE` | 3.930 | 3.959 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:reactjs__react-transition-group.2989b5b8:root` | `EXACT-SOURCE-RESET` | 0.485 | 0.487 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:redux-saga__redux-saga.a4ace10d:root` | `EXACT-SOURCE-MATERIALIZE` | 12.235 | 12.663 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:redux-saga__redux-saga.a4ace10d:root` | `EXACT-SOURCE-RESET` | 3.052 | 3.070 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:refined-github__refined-github.d4a7c3fb:root` | `EXACT-SOURCE-MATERIALIZE` | 12.860 | 13.006 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:refined-github__refined-github.d4a7c3fb:root` | `EXACT-SOURCE-RESET` | 2.408 | 2.459 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:remy__nodemon.daad5c16:root` | `EXACT-SOURCE-MATERIALIZE` | 12.597 | 12.956 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:remy__nodemon.daad5c16:root` | `EXACT-SOURCE-RESET` | 2.929 | 3.132 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:segmentio__evergreen.9b774aee:root` | `EXACT-SOURCE-MATERIALIZE` | 30.121 | 33.003 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:segmentio__evergreen.9b774aee:root` | `EXACT-SOURCE-RESET` | 15.109 | 15.540 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:strapi__strapi.e5b87a54:root` | `EXACT-SOURCE-MATERIALIZE` | 151.994 | 155.326 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:strapi__strapi.e5b87a54:root` | `EXACT-SOURCE-RESET` | 79.880 | 82.524 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:sveltejs__svelte.6c9717a9:root` | `EXACT-SOURCE-MATERIALIZE` | 194.414 | 229.827 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:sveltejs__svelte.6c9717a9:root` | `EXACT-SOURCE-RESET` | 114.386 | 114.997 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:svg__svgo.c06d8f68:root` | `EXACT-SOURCE-MATERIALIZE` | 15.276 | 15.865 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:svg__svgo.c06d8f68:root` | `EXACT-SOURCE-RESET` | 3.396 | 5.509 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:tinacms__tinacms.dffb104f:root` | `EXACT-SOURCE-MATERIALIZE` | 47.241 | 49.162 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:tinacms__tinacms.dffb104f:root` | `EXACT-SOURCE-RESET` | 24.637 | 25.139 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:trpc__trpc.2f40ba93:root` | `EXACT-SOURCE-MATERIALIZE` | 30.259 | 35.297 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:trpc__trpc.2f40ba93:root` | `EXACT-SOURCE-RESET` | 16.019 | 16.442 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:ueberdosis__tiptap.2d6de06c:root` | `EXACT-SOURCE-MATERIALIZE` | 48.184 | 50.649 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:ueberdosis__tiptap.2d6de06c:root` | `EXACT-SOURCE-RESET` | 26.102 | 27.697 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:umijs__qiankun.693cdde7:root` | `EXACT-SOURCE-MATERIALIZE` | 12.905 | 12.986 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:umijs__qiankun.693cdde7:root` | `EXACT-SOURCE-RESET` | 3.092 | 3.292 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:vitejs__vite.8b47ff76:root` | `EXACT-SOURCE-MATERIALIZE` | 60.439 | 62.825 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:vitejs__vite.8b47ff76:root` | `EXACT-SOURCE-RESET` | 31.528 | 33.614 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:voideditor__void.17e7a5b1:root` | `EXACT-SOURCE-MATERIALIZE` | 245.777 | 255.281 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:voideditor__void.17e7a5b1:root` | `EXACT-SOURCE-RESET` | 120.352 | 137.751 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:webpack__webpack.24e3c2d2:root` | `EXACT-SOURCE-MATERIALIZE` | 221.724 | 241.140 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:webpack__webpack.24e3c2d2:root` | `EXACT-SOURCE-RESET` | 125.659 | 215.451 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:websockets__ws.726c3732:root` | `EXACT-SOURCE-MATERIALIZE` | 3.613 | 3.704 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:websockets__ws.726c3732:root` | `EXACT-SOURCE-RESET` | 0.439 | 0.465 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:welldone-software__why-did-you-render.3ec3512d:root` | `EXACT-SOURCE-MATERIALIZE` | 5.732 | 6.174 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `source_overlay:welldone-software__why-did-you-render.3ec3512d:root` | `EXACT-SOURCE-RESET` | 0.999 | 1.018 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:Shopify__draggable.8a1eed57:root:jest:75fa7c4af02e` | `EXACT-TEST-CACHE-COLD` | 1212.482 | 1262.285 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:Shopify__draggable.8a1eed57:root:jest:75fa7c4af02e` | `EXACT-TEST-CACHE-HIT` | 1220.549 | 1273.803 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:advplyr__audiobookshelf.626596b1:root:mocha:12f5a03dadc2` | `EXACT-TEST-CACHE-COLD` | 1085.348 | 1099.335 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:advplyr__audiobookshelf.626596b1:root:mocha:12f5a03dadc2` | `EXACT-TEST-CACHE-HIT` | 1084.831 | 1138.472 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:homebridge__homebridge.3a341e08:root:jest:cb88c6110fb6` | `EXACT-TEST-CACHE-COLD` | 1790.881 | 1825.742 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:homebridge__homebridge.3a341e08:root:jest:cb88c6110fb6` | `EXACT-TEST-CACHE-HIT` | 1775.963 | 1787.374 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:iamkun__dayjs.c8a26460:root:jest:9ed6e5f7fd04` | `EXACT-TEST-CACHE-COLD` | 6548.672 | 7734.467 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:iamkun__dayjs.c8a26460:root:jest:9ed6e5f7fd04` | `EXACT-TEST-CACHE-HIT` | 5890.367 | 6949.802 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:josdejong__jsoneditor.0319b213:root:mocha:be56cc981d38` | `EXACT-TEST-CACHE-COLD` | 2111.437 | 2134.797 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:josdejong__jsoneditor.0319b213:root:mocha:be56cc981d38` | `EXACT-TEST-CACHE-HIT` | 1335.356 | 1369.190 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:nock__nock.e7418da2:root:jest:bf94886cefe6` | `EXACT-TEST-CACHE-COLD` | 668.322 | 724.279 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:nock__nock.e7418da2:root:jest:bf94886cefe6` | `EXACT-TEST-CACHE-HIT` | 664.103 | 682.165 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:sveltejs__svelte.6c9717a9:root:vitest:85b839d59475` | `EXACT-TEST-CACHE-COLD` | 2665.861 | 2748.528 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:sveltejs__svelte.6c9717a9:root:vitest:85b839d59475` | `EXACT-TEST-CACHE-HIT` | 2669.738 | 2680.272 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:ueberdosis__tiptap.2d6de06c:root:vitest:85ad102bc603` | `EXACT-TEST-CACHE-COLD` | 3982.473 | 4089.894 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:ueberdosis__tiptap.2d6de06c:root:vitest:85ad102bc603` | `EXACT-TEST-CACHE-HIT` | 4004.541 | 4039.606 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:webpack__webpack.24e3c2d2:root:jest:8138d968425d` | `EXACT-TEST-CACHE-COLD` | 2020.379 | 2059.901 | 7 | `env:0fd7b54e0a2a55d4208d` |
| `test_transform_cache:webpack__webpack.24e3c2d2:root:jest:8138d968425d` | `EXACT-TEST-CACHE-HIT` | 1974.733 | 2079.492 | 7 | `env:0fd7b54e0a2a55d4208d` |

## Key Measured Transitions

- Node: Node 18/20/22 cold start, exact hit, and all 3x3 directions are present in `node_switch_matrix.csv`.
- Package manager: npm, pnpm, Yarn Classic, Yarn Berry, and Bun exact-version observations are present in `pm_switch_matrix.csv`.
- Original generic environment: Chromium and Firefox process/profile/context actions are measured; WebKit remains explicitly unsupported there.
- Original generic environment: Redis daemon and SQLite snapshot/private-layer actions are measured; MongoDB/PostgreSQL/MySQL remain unsupported because that run lacked Docker/binaries. The later exact-workload host has Docker and separately measured 14 rootfs objects.
- Dependency view exact run: `{"blocked": 21, "manual_review": 12, "measured": 31}`.
- Repo/source/build/test/native/rootfs exact statuses: see `unmeasured_objects.json`; no object remains implicit (`unmeasured=0`).

## Decision

Phase 2 is **passed_with_constraints**. Every scheduler-relevant exact object is measured or has an explicit blocked/unsupported/manual-review/failed status. Blocked objects are accounted, but they are not latency measurements and must not be treated as zero.

This output is suitable as a calibration CostDB and as the input to targeted completion work. It must not be interpreted as proof that every real Profile transition has been measured.

Generated from NodeLite-Schduler `out/`; catalog statuses and gaps are preserved in `catalog_status.json`, `coverage.md`, and `environment_gaps.md`.
