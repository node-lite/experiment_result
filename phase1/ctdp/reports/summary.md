# SWE-smith Dependency Preparation Summary

Generated: 2026-09-04T17:24:16.362544+00:00

- Input profile count: 64
- Discovered profile count: 64
- Failed discovery count: 0

## Package managers

- Profile distribution (64 profiles): `{"bun": 2, "npm": 33, "pnpm": 12, "yarn": 17}`
- Dependency-root distribution (65 roots): `{"bun": 2, "npm": 34, "pnpm": 12, "yarn": 17}`
- Versions (dependency roots): `{"1.2.18": 1, "1.22.21": 1, "1.22.22": 4, "1.3.7": 1, "10": 1, "10.17.1": 1, "10.27.0": 1, "10.28.2": 1, "10.4.0": 1, "3.2.3": 1, "3.8.7": 1, "4.0.2": 1, "4.10.3": 1, "4.12.0": 1, "4.9.1": 1, "9.12.2": 1, "9.15.0": 1, "9.15.4": 1, "9.15.5": 1, "9.4.0": 1, "unknown": 42}`

## Lockfile classification

- Counts: `{"authoritative_existing": 10, "existing_requires_resolution": 37, "missing_requires_resolution": 8, "unsupported_or_manual_review": 10}`
- Authoritative / re-resolution / missing / manual-review: 10 / 37 / 8 / 10

- Resolution success/failure: 55/9
- Resolution time total/P50/P95/max (ms): 8546532/35036.0/420972.4/445440

## Artifacts

- Dependency references: 101967
- Unique logical package versions: 27259
- Unique immutable artifacts: 33769
- CAS artifact bytes: 17605669618
- CAS directory bytes (including metadata): 31876726845
- Dedup bytes before/after: 25309178036/17605669618 (measured after: True)
- Dedup ratio: 0.6688242274461346
- Prefetch success/failure: 32488/1
- CAS integrity failures: 0

## Native cache warmup

- Cache bytes by PM: `{"bun": 3085316560, "npm": 750216, "pnpm": 13420147610, "yarn": 8422830791}`
- Success/failure/status by PM: `{"bun": {"cache_bytes": 3085316560, "elapsed_ms": 74129, "failed_count": 0, "imported": 2056, "manager": "bun", "policies": [{"cache_bytes": 1270623850, "failed_count": 0, "imported": 469, "status": "success", "variant": null, "version": "1.2.18"}, {"cache_bytes": 1814692710, "failed_count": 0, "imported": 1587, "status": "success", "variant": null, "version": "1.3.7"}], "status": "success"}, "npm": {"cache_bytes": 750216, "elapsed_ms": 16775, "failed_count": 0, "imported": 11972, "manager": "npm", "policies": [{"cache_bytes": 750216, "failed_count": 0, "imported": 11972, "status": "success", "variant": null, "version": "9.2.0"}], "status": "success"}, "pnpm": {"cache_bytes": 13420147610, "elapsed_ms": 421955, "failed_count": 0, "imported": 20534, "manager": "pnpm", "policies": [{"cache_bytes": 833605767, "failed_count": 0, "imported": 2469, "status": "success", "variant": null, "version": "10"}, {"cache_bytes": 994417009, "failed_count": 0, "imported": 1275, "status": "success", "variant": null, "version": "10.17.1"}, {"cache_bytes": 2084456889, "failed_count": 0, "imported": 2210, "status": "success", "variant": null, "version": "10.27.0"}, {"cache_bytes": 603665599, "failed_count": 0, "imported": 1058, "status": "success", "variant": null, "version": "10.28.2"}, {"cache_bytes": 175118075, "failed_count": 0, "imported": 455, "status": "success", "variant": null, "version": "10.4.0"}, {"cache_bytes": 2363791838, "failed_count": 0, "imported": 3439, "status": "success", "variant": null, "version": "9.12.2"}, {"cache_bytes": 535041918, "failed_count": 0, "imported": 1489, "status": "success", "variant": null, "version": "9.15.0"}, {"cache_bytes": 453126591, "failed_count": 0, "imported": 1271, "status": "success", "variant": null, "version": "9.15.4"}, {"cache_bytes": 3518898341, "failed_count": 0, "imported": 4469, "status": "success", "variant": null, "version": "9.15.5"}, {"cache_bytes": 1858025583, "failed_count": 0, "imported": 2399, "status": "success", "variant": null, "version": "9.4.0"}], "status": "success"}, "yarn": {"cache_bytes": 8422830791, "elapsed_ms": 537718, "failed_count": 32, "imported": 14645, "manager": "yarn", "policies": [{"cache_bytes": 352902856, "failed_count": 0, "imported": 3033, "status": "success", "variant": "berry", "version": "3.2.3"}, {"cache_bytes": 36979236, "failed_count": 0, "imported": 624, "status": "success", "variant": "berry", "version": "3.8.7"}, {"cache_bytes": 819992864, "failed_count": 0, "imported": 2182, "status": "success", "variant": "berry", "version": "4.0.2"}, {"cache_bytes": 151207157, "failed_count": 0, "imported": 796, "status": "success", "variant": "berry", "version": "4.10.3"}, {"cache_bytes": 1073819349, "failed_count": 0, "imported": 2953, "status": "success", "variant": "berry", "version": "4.12.0"}, {"cache_bytes": 251413539, "failed_count": 0, "imported": 1460, "status": "success", "variant": "berry", "version": "4.9.1"}, {"cache_bytes": 1010073287, "failed_count": 0, "imported": 2292, "status": "success", "variant": "classic", "version": "1.22.21"}, {"cache_bytes": 4726442503, "failed_count": 32, "imported": 1305, "status": "partial", "variant": "classic", "version": "1.22.22"}], "status": "partial"}}`

## Performance

- Stage timing summaries (ms): `{"discover": {"count": 64, "max": 401911, "p50": 1093.5, "p95": 1571.249999999997, "total": 654230}, "normalize": {"count": 65, "max": 6606, "p50": 14.0, "p95": 1372.8, "total": 20458}, "prefetch": {"count": 32489, "max": 2212963, "p50": 4.0, "p95": 460.59999999999854, "total": 43281948}, "resolve": {"count": 65, "max": 445440, "p50": 35036.0, "p95": 420972.4, "total": 8546532}, "validate": {"count": 64, "max": 69813, "p50": 4414.5, "p95": 44723.949999999975, "total": 633738}, "warm-cache": {"count": 21, "max": 191657, "p50": 36815.0, "p95": 127762.0, "total": 1050577}}`

## Dynamic validation

- Results: `{"external_artifact_miss": 16, "native_or_system_dependency_failure": 0, "other_failure": 30, "success": 18}`
- Profiles with external artifact misses: `["swesmith/bootstrap-vue__bootstrap-vue.9a246f45", "swesmith/brianc__node-postgres.ecff60dc", "swesmith/Effect-TS__effect.5df4da10", "swesmith/enzymejs__enzyme.61e1b47c", "swesmith/fabricjs__fabric.js.6742471c", "swesmith/foambubble__foam.2cac8162", "swesmith/jaredpalmer__formik.91475adb", "swesmith/microsoft__vscode.4166e90a", "swesmith/NativeScript__NativeScript.3d6a4392", "swesmith/nestjs__nest.346c9543", "swesmith/Redocly__redoc.d41fd46f", "swesmith/redux-saga__redux-saga.a4ace10d", "swesmith/segmentio__evergreen.9b774aee", "swesmith/Shopify__draggable.8a1eed57", "swesmith/sveltejs__svelte.6c9717a9", "swesmith/voideditor__void.17e7a5b1"]`
- First-run Internet bytes: 9234461362
- Second-run Internet bytes: 3582234320
