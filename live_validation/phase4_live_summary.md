# Phase 4 Live Transition Validation

Status: **live_host_object_medians**

- Selected profiles: `20`
- Directed pairs evaluated: `380`
- Sampled pairs: `100`

## Error Metrics
- MAE: `8658.992` ms
- Median Absolute Error: `3748.386` ms
- P95 Absolute Error: `27669.384` ms
- Bias: `8315.192` ms
- Pearson: `0.7631`
- Spearman: `0.8758`

## Sample Metrics
- MAE: `24974.297` ms
- Median Absolute Error: `23689.380` ms
- P95 Absolute Error: `62838.269` ms
- Bias: `24914.875` ms
- Pearson: `0.4960`
- Spearman: `0.5976`

## Top Errors
1. `swesmith/bootstrap-vue__bootstrap-vue.9a246f45` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `24877.342` ms, measured `87715.611` ms, abs err `62838.269` ms
2. `swesmith/bpampuch__pdfmake.719e7314` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `24877.342` ms, measured `87715.611` ms, abs err `62838.269` ms
3. `swesmith/enzymejs__enzyme.61e1b47c` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `24877.342` ms, measured `87715.611` ms, abs err `62838.269` ms
4. `swesmith/fabricjs__fabric.js.6742471c` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `24877.342` ms, measured `87715.611` ms, abs err `62838.269` ms
5. `swesmith/foliojs__pdfkit.d0108157` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `24877.342` ms, measured `87715.611` ms, abs err `62838.269` ms
6. `swesmith/josdejong__mathjs.04e6e2d7` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `24877.342` ms, measured `87715.611` ms, abs err `62838.269` ms
7. `swesmith/Netflix__falcor.39d64776` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `24877.342` ms, measured `87715.611` ms, abs err `62838.269` ms
8. `swesmith/Redocly__redoc.d41fd46f` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `24877.342` ms, measured `87715.611` ms, abs err `62838.269` ms
9. `swesmith/strapi__strapi.e5b87a54` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `24877.342` ms, measured `87715.611` ms, abs err `62838.269` ms
10. `swesmith/trpc__trpc.2f40ba93` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `24877.342` ms, measured `87715.611` ms, abs err `62838.269` ms
11. `swesmith/vitejs__vite.8b47ff76` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `24877.342` ms, measured `87715.611` ms, abs err `62838.269` ms
12. `swesmith/FuelLabs__fuels-ts.b3f37c91` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `24855.871` ms, measured `87682.273` ms, abs err `62826.402` ms
13. `swesmith/foambubble__foam.2cac8162` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `25048.433` ms, measured `87715.611` ms, abs err `62667.179` ms
14. `swesmith/ReactiveX__rxjs.c15b37f8` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `25048.433` ms, measured `87715.611` ms, abs err `62667.179` ms
15. `swesmith/antvis__G6.91c0ac85` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `25026.962` ms, measured `87682.273` ms, abs err `62655.311` ms
16. `swesmith/Automattic__mongoose.5f57a5bb` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `29227.246` ms, measured `87715.611` ms, abs err `58488.365` ms
17. `swesmith/caolan__async.23dbf76a` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `29227.246` ms, measured `87715.611` ms, abs err `58488.365` ms
18. `swesmith/novnc__noVNC.d44f7e04` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `29227.246` ms, measured `87715.611` ms, abs err `58488.365` ms
19. `swesmith/nock__nock.e7418da2` -> `swesmith/ueberdosis__tiptap.2d6de06c`: pred `29205.776` ms, measured `87682.273` ms, abs err `58476.498` ms
20. `swesmith/ueberdosis__tiptap.2d6de06c` -> `swesmith/ReactiveX__rxjs.c15b37f8`: pred `12013.628` ms, measured `38061.585` ms, abs err `26047.957` ms

## Notes
- This report is derived from live exact-host measurements in `out/exact-workload` and is not a replay artifact.
- The pair model uses object-level medians measured on the live host and a kind-level predictor for comparison.
