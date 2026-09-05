# SWE-smith Dependency Preparation Summary

Generated: 2026-09-05T11:37:59.936331+00:00

- Input profile count: 64
- Discovered profile count: 64
- Failed discovery count: 0

## Package managers

- Profile distribution (64 profiles): `{"bun": 2, "npm": 33, "pnpm": 12, "yarn": 17}`
- Dependency-root distribution (65 roots): `{"bun": 2, "npm": 34, "pnpm": 12, "yarn": 17}`
- Versions (dependency roots): `{"1.2.18": 1, "1.22.21": 1, "1.22.22": 4, "1.3.7": 1, "10": 1, "10.17.1": 1, "10.27.0": 1, "10.28.2": 1, "10.4.0": 1, "3.2.3": 1, "3.8.7": 1, "4.0.2": 1, "4.10.3": 1, "4.12.0": 1, "4.9.1": 1, "9.12.2": 1, "9.15.0": 1, "9.15.4": 1, "9.15.5": 1, "9.4.0": 1, "unknown": 42}`

## Lockfile classification

- Counts: `{"authoritative_existing": 10, "existing_requires_resolution": 44, "missing_requires_resolution": 8, "unsupported_or_manual_review": 3}`
- Authoritative / re-resolution / missing / manual-review: 10 / 44 / 8 / 3

- Resolution success/failure: 62/2
- Resolution time total/P50/P95/max (ms): 1484196/4714.0/93847.3999999999/369942

## Artifacts

- Dependency references: 105097
- Unique logical package versions: 27691
- Unique immutable artifacts: 34462
- CAS artifact bytes: 17672905706
- CAS directory bytes (including metadata): 32306292093
- Dedup bytes before/after: 25418483974/17672905706 (measured after: True)
- Dedup ratio: 0.6720933994310019
- Prefetch success/failure: 32940/1
- CAS integrity failures: 0

## Native cache warmup

- Cache bytes by PM: `{"bun": 3085316560, "npm": 750216, "pnpm": 13420147610, "yarn": 8422830791}`
- Success/failure/status by PM: `{"bun": {"cache_bytes": 3085316560, "elapsed_ms": 74129, "failed_count": 0, "imported": 2056, "manager": "bun", "policies": [{"cache_bytes": 1270623850, "failed_count": 0, "imported": 469, "status": "success", "variant": null, "version": "1.2.18"}, {"cache_bytes": 1814692710, "failed_count": 0, "imported": 1587, "status": "success", "variant": null, "version": "1.3.7"}], "status": "success"}, "npm": {"cache_bytes": 750216, "elapsed_ms": 16775, "failed_count": 0, "imported": 11972, "manager": "npm", "policies": [{"cache_bytes": 750216, "failed_count": 0, "imported": 11972, "status": "success", "variant": null, "version": "9.2.0"}], "status": "success"}, "pnpm": {"cache_bytes": 13420147610, "elapsed_ms": 421955, "failed_count": 0, "imported": 20534, "manager": "pnpm", "policies": [{"cache_bytes": 833605767, "failed_count": 0, "imported": 2469, "status": "success", "variant": null, "version": "10"}, {"cache_bytes": 994417009, "failed_count": 0, "imported": 1275, "status": "success", "variant": null, "version": "10.17.1"}, {"cache_bytes": 2084456889, "failed_count": 0, "imported": 2210, "status": "success", "variant": null, "version": "10.27.0"}, {"cache_bytes": 603665599, "failed_count": 0, "imported": 1058, "status": "success", "variant": null, "version": "10.28.2"}, {"cache_bytes": 175118075, "failed_count": 0, "imported": 455, "status": "success", "variant": null, "version": "10.4.0"}, {"cache_bytes": 2363791838, "failed_count": 0, "imported": 3439, "status": "success", "variant": null, "version": "9.12.2"}, {"cache_bytes": 535041918, "failed_count": 0, "imported": 1489, "status": "success", "variant": null, "version": "9.15.0"}, {"cache_bytes": 453126591, "failed_count": 0, "imported": 1271, "status": "success", "variant": null, "version": "9.15.4"}, {"cache_bytes": 3518898341, "failed_count": 0, "imported": 4469, "status": "success", "variant": null, "version": "9.15.5"}, {"cache_bytes": 1858025583, "failed_count": 0, "imported": 2399, "status": "success", "variant": null, "version": "9.4.0"}], "status": "success"}, "yarn": {"cache_bytes": 8422830791, "elapsed_ms": 537718, "failed_count": 32, "imported": 14645, "manager": "yarn", "policies": [{"cache_bytes": 352902856, "failed_count": 0, "imported": 3033, "status": "success", "variant": "berry", "version": "3.2.3"}, {"cache_bytes": 36979236, "failed_count": 0, "imported": 624, "status": "success", "variant": "berry", "version": "3.8.7"}, {"cache_bytes": 819992864, "failed_count": 0, "imported": 2182, "status": "success", "variant": "berry", "version": "4.0.2"}, {"cache_bytes": 151207157, "failed_count": 0, "imported": 796, "status": "success", "variant": "berry", "version": "4.10.3"}, {"cache_bytes": 1073819349, "failed_count": 0, "imported": 2953, "status": "success", "variant": "berry", "version": "4.12.0"}, {"cache_bytes": 251413539, "failed_count": 0, "imported": 1460, "status": "success", "variant": "berry", "version": "4.9.1"}, {"cache_bytes": 1010073287, "failed_count": 0, "imported": 2292, "status": "success", "variant": "classic", "version": "1.22.21"}, {"cache_bytes": 4726442503, "failed_count": 32, "imported": 1305, "status": "partial", "variant": "classic", "version": "1.22.22"}], "status": "partial"}}`

## Performance

- Stage timing summaries (ms): `{"discover": {"count": 64, "max": 401911, "p50": 1093.5, "p95": 1571.249999999997, "total": 654230}, "normalize": {"count": 65, "max": 6289, "p50": 15.0, "p95": 1437.9999999999998, "total": 20444}, "prefetch": {"count": 32941, "max": 498944, "p50": 2.0, "p95": 10.0, "total": 3056385}, "resolve": {"count": 65, "max": 369942, "p50": 4714.0, "p95": 93847.3999999999, "total": 1484196}, "validate": {"count": 64, "max": 138745, "p50": 6574.5, "p95": 54508.049999999945, "total": 1018246}, "warm-cache": {"count": 21, "max": 191657, "p50": 36815.0, "p95": 127762.0, "total": 1050577}}`

## Dynamic validation

- Results: `{"external_artifact_miss": 30, "native_or_system_dependency_failure": 3, "other_failure": 12, "success": 19}`
- Profiles with external artifact misses: `["swesmith/antvis__G6.91c0ac85", "swesmith/bluesky-social__social-app.cbd48c85", "swesmith/bootstrap-vue__bootstrap-vue.9a246f45", "swesmith/brianc__node-postgres.ecff60dc", "swesmith/directus__directus.ac922d18", "swesmith/Effect-TS__effect.5df4da10", "swesmith/emotion-js__emotion.b882bcba", "swesmith/enzymejs__enzyme.61e1b47c", "swesmith/fabricjs__fabric.js.6742471c", "swesmith/foambubble__foam.2cac8162", "swesmith/foliojs__pdfkit.d0108157", "swesmith/FuelLabs__fuels-ts.b3f37c91", "swesmith/jaredpalmer__formik.91475adb", "swesmith/microsoft__vscode.4166e90a", "swesmith/NativeScript__NativeScript.3d6a4392", "swesmith/nestjs__nest.346c9543", "swesmith/OpenCut-app__OpenCut.e84c0cfd", "swesmith/payloadcms__payload.8f660355", "swesmith/react-hook-form__react-hook-form.3adba2b8", "swesmith/ReactiveX__rxjs.c15b37f8", "swesmith/Redocly__redoc.d41fd46f", "swesmith/redux-saga__redux-saga.a4ace10d", "swesmith/segmentio__evergreen.9b774aee", "swesmith/Shopify__draggable.8a1eed57", "swesmith/sveltejs__svelte.6c9717a9", "swesmith/tinacms__tinacms.dffb104f", "swesmith/trpc__trpc.2f40ba93", "swesmith/umijs__qiankun.693cdde7", "swesmith/webpack__webpack.24e3c2d2", "swesmith/welldone-software__why-did-you-render.3ec3512d"]`
- First-run Internet bytes: 9234461362
- Second-run Internet bytes: 213832627

## Targeted external artifact revalidation

The post-fix targeted rerun covers the 21 actionable external-artifact profiles from the baseline classification: 10 registry/proxy cases, 5 CAS tarball cases, and 6 Git/VCS cases.

- Scope: 21 profiles, G1 dependency preparation and local-registry install only.
- Successful targeted reruns: 21 / 21.
- Remaining external artifact misses in this scope: 0 / 21.
- Outbound requests during targeted reruns: 0.
- Evidence: `phase1/external_artifact_revalidation.json`.

This targeted result does not replace the baseline 64-profile dynamic validation above. Full G2 lifecycle/build validation has not been rerun for all 64 profiles, so the report remains partial rather than claiming a full Phase 1 pass.
