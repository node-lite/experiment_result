# Phase 4 Transition Cost Model Validation (derived exact-oracle replay)

- Calibration environment: `env:7a9cda66bc6b151a7886`
- Full directed pairs evaluated: `4032` / `4032`
- Fully predictable pairs: `4032`
- Partial pairs: `0`
- Unknown pairs: `0`
- Sampled pairs: `100`
- Phase 3 anchor pairs in sample: `63`

## Error Metrics

- MAE: `19744.347` ms
- Median Absolute Error: `18022.738` ms
- P95 Absolute Error: `39640.127` ms
- Bias: `-19744.347` ms
- Pearson: `0.9975`
- Spearman: `0.9946`

## Sample Metrics

- MAE: `32453.190` ms
- Median Absolute Error: `29164.957` ms
- P95 Absolute Error: `61166.278` ms
- Bias: `-32453.190` ms
- Pearson: `0.9981`
- Spearman: `0.9930`

## Pair Coverage

- same_node_same_rootfs: `714`
- same_node_diff_rootfs: `792`
- diff_node_same_rootfs: `0`
- diff_node_diff_rootfs: `2526`
- same_build_tool: `786`
- same_test_tool: `942`
- same_dependency_view: `0`
- same_native_bundle: `36`
- high_overlap: `0`
- low_overlap: `3318`
- native_abi_change: `2526`
- rootfs_change: `3318`

## Top Errors
1. `swesmith/fabricjs__fabric.js.6742471c` -> `swesmith/nestjs__nest.346c9543`: pred `426691.426` ms, measured `365111.681` ms, abs err `61579.745` ms
2. `swesmith/marko-js__marko.24b9402c` -> `swesmith/nestjs__nest.346c9543`: pred `426691.426` ms, measured `365111.681` ms, abs err `61579.745` ms
3. `swesmith/payloadcms__payload.8f660355` -> `swesmith/nestjs__nest.346c9543`: pred `426691.426` ms, measured `365111.681` ms, abs err `61579.745` ms
4. `swesmith/strapi__strapi.e5b87a54` -> `swesmith/nestjs__nest.346c9543`: pred `426691.426` ms, measured `365111.681` ms, abs err `61579.745` ms
5. `swesmith/webpack__webpack.24e3c2d2` -> `swesmith/nestjs__nest.346c9543`: pred `426691.426` ms, measured `365111.681` ms, abs err `61579.745` ms
6. `swesmith/bluesky-social__social-app.cbd48c85` -> `swesmith/nestjs__nest.346c9543`: pred `426925.780` ms, measured `365781.263` ms, abs err `61144.517` ms
7. `swesmith/Effect-TS__effect.5df4da10` -> `swesmith/nestjs__nest.346c9543`: pred `426925.780` ms, measured `365781.263` ms, abs err `61144.517` ms
8. `swesmith/homebridge__homebridge.3a341e08` -> `swesmith/nestjs__nest.346c9543`: pred `426925.780` ms, measured `365781.263` ms, abs err `61144.517` ms
9. `swesmith/josdejong__jsoneditor.0319b213` -> `swesmith/nestjs__nest.346c9543`: pred `426925.780` ms, measured `365781.263` ms, abs err `61144.517` ms
10. `swesmith/svg__svgo.c06d8f68` -> `swesmith/nestjs__nest.346c9543`: pred `426925.780` ms, measured `365781.263` ms, abs err `61144.517` ms
11. `swesmith/tinacms__tinacms.dffb104f` -> `swesmith/nestjs__nest.346c9543`: pred `426925.780` ms, measured `365781.263` ms, abs err `61144.517` ms
12. `swesmith/welldone-software__why-did-you-render.3ec3512d` -> `swesmith/nestjs__nest.346c9543`: pred `426925.780` ms, measured `365781.263` ms, abs err `61144.517` ms
13. `swesmith/brianc__node-postgres.ecff60dc` -> `swesmith/nestjs__nest.346c9543`: pred `426663.833` ms, measured `365781.263` ms, abs err `60882.570` ms
14. `swesmith/ReactiveX__rxjs.c15b37f8` -> `swesmith/nestjs__nest.346c9543`: pred `426663.833` ms, measured `365781.263` ms, abs err `60882.570` ms
15. `swesmith/refined-github__refined-github.d4a7c3fb` -> `swesmith/mochajs__mocha.410ce0d2`: pred `333120.635` ms, measured `282049.519` ms, abs err `51071.116` ms
16. `swesmith/FuelLabs__fuels-ts.b3f37c91` -> `swesmith/Shopify__draggable.8a1eed57`: pred `325786.122` ms, measured `275393.800` ms, abs err `50392.322` ms
17. `swesmith/Shopify__draggable.8a1eed57` -> `swesmith/FuelLabs__fuels-ts.b3f37c91`: pred `325786.122` ms, measured `275393.800` ms, abs err `50392.322` ms
18. `swesmith/ueberdosis__tiptap.2d6de06c` -> `swesmith/FuelLabs__fuels-ts.b3f37c91`: pred `325786.122` ms, measured `275393.800` ms, abs err `50392.322` ms
19. `swesmith/ueberdosis__tiptap.2d6de06c` -> `swesmith/Shopify__draggable.8a1eed57`: pred `325786.122` ms, measured `275393.800` ms, abs err `50392.322` ms
20. `swesmith/ajayyy__SponsorBlock.dfddffbc` -> `swesmith/reactjs__react-transition-group.2989b5b8`: pred `325786.122` ms, measured `275509.696` ms, abs err `50276.426` ms

## Asymmetry
- Evaluated reverse pairs: `2016`
1. `swesmith/babel__babel.2ea3fc8f` <-> `swesmith/nestjs__nest.346c9543`: A->B `392406.088` ms, B->A `26665.088` ms, delta `365741.000` ms
2. `swesmith/coder__code-server.e90504b8` <-> `swesmith/nestjs__nest.346c9543`: A->B `392406.088` ms, B->A `26665.088` ms, delta `365741.000` ms
3. `swesmith/directus__directus.ac922d18` <-> `swesmith/nestjs__nest.346c9543`: A->B `392406.088` ms, B->A `26665.088` ms, delta `365741.000` ms
4. `swesmith/humanlayer__12-factor-agents.d20c7283` <-> `swesmith/nestjs__nest.346c9543`: A->B `365781.263` ms, B->A `40.263` ms, delta `365741.000` ms
5. `swesmith/Automattic__mongoose.5f57a5bb` <-> `swesmith/nestjs__nest.346c9543`: A->B `392406.088` ms, B->A `33213.760` ms, delta `359192.328` ms
6. `swesmith/balderdashy__sails.ffebacc5` <-> `swesmith/nestjs__nest.346c9543`: A->B `392406.088` ms, B->A `33213.760` ms, delta `359192.328` ms
7. `swesmith/mholt__PapaParse.b10b87ef` <-> `swesmith/nestjs__nest.346c9543`: A->B `392406.088` ms, B->A `33213.760` ms, delta `359192.328` ms
8. `swesmith/necolas__react-native-web.a9de220b` <-> `swesmith/nestjs__nest.346c9543`: A->B `392406.088` ms, B->A `33213.760` ms, delta `359192.328` ms
9. `swesmith/nestjs__nest.346c9543` <-> `swesmith/remy__nodemon.daad5c16`: A->B `33213.760` ms, B->A `392406.088` ms, delta `359192.328` ms
10. `swesmith/nestjs__nest.346c9543` <-> `swesmith/websockets__ws.726c3732`: A->B `33213.760` ms, B->A `392406.088` ms, delta `359192.328` ms
11. `swesmith/nestjs__nest.346c9543` <-> `swesmith/novnc__noVNC.d44f7e04`: A->B `6588.935` ms, B->A `365781.263` ms, delta `359192.328` ms
12. `swesmith/nestjs__nest.346c9543` <-> `swesmith/nightwatchjs__nightwatch.54c8550c`: A->B `33999.601` ms, B->A `392406.088` ms, delta `358406.487` ms
13. `swesmith/caolan__async.23dbf76a` <-> `swesmith/nestjs__nest.346c9543`: A->B `392406.088` ms, B->A `39762.432` ms, delta `352643.656` ms
14. `swesmith/nestjs__nest.346c9543` <-> `swesmith/nock__nock.e7418da2`: A->B `39762.432` ms, B->A `392406.088` ms, delta `352643.656` ms
15. `swesmith/advplyr__audiobookshelf.626596b1` <-> `swesmith/nestjs__nest.346c9543`: A->B `392406.088` ms, B->A `67074.333` ms, delta `325331.756` ms
16. `swesmith/babel__babel.2ea3fc8f` <-> `swesmith/voideditor__void.17e7a5b1`: A->B `309353.138` ms, B->A `26665.088` ms, delta `282688.050` ms
17. `swesmith/coder__code-server.e90504b8` <-> `swesmith/voideditor__void.17e7a5b1`: A->B `309353.138` ms, B->A `26665.088` ms, delta `282688.050` ms
18. `swesmith/directus__directus.ac922d18` <-> `swesmith/voideditor__void.17e7a5b1`: A->B `309353.138` ms, B->A `26665.088` ms, delta `282688.050` ms
19. `swesmith/humanlayer__12-factor-agents.d20c7283` <-> `swesmith/voideditor__void.17e7a5b1`: A->B `309353.138` ms, B->A `26665.088` ms, delta `282688.050` ms
20. `swesmith/babel__babel.2ea3fc8f` <-> `swesmith/mochajs__mocha.410ce0d2`: A->B `308567.297` ms, B->A `26665.088` ms, delta `281902.209` ms

## Decision
Phase 4 is **sufficient for scheduler integration** as a derived exact-oracle validation, but it is still a replay model rather than a fresh live host pair-run.

## Notes
- Exact anchors from phase 3 consecutive sequence: `63`
- Browser and database resource kinds do not appear in the fixed 64-profile slice, so their coverage is zero here.
- Missing 0-cost assumptions are avoided; any absent transition falls back to kind-level medians instead of zero.
