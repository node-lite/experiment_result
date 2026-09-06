# Phase 7 Online Sliding-Window Adaptation (observation-stream replay)

Status: **passed_with_constraints (observation-stream replay)**

## Input
- Phase 2 observation stream: `phase2/object_action_observations.jsonl`
- Calibration environment: `env:7a9cda66bc6b151a7886`
- Drift environment: `env:0fd7b54e0a2a55d4208d`
- Window size: `5`
- Rolling leader lookback: `100`

## Coverage
- Online observations: `8589`
- Calibration observations: `5222`
- Drift observations: `3367`
- Action keys with at least one sample: `1192`
- Action keys with full 5-sample windows: `1192`
- Resource kinds with at least one sample: `38`
- Resource kinds with full 5-sample windows: `38`

## Main Results
- Static MAE: `489.601` ms
- Latest MAE: `454.552` ms
- FIFO-5 Mean MAE: `366.999` ms
- FIFO-5 Median MAE: `343.644` ms
- Static P95 error: `1538.846` ms
- Latest P95 error: `644.003` ms
- FIFO-5 Mean P95 error: `1532.891` ms
- FIFO-5 Median P95 error: `286.888` ms
- Static bias: `-429.976` ms
- Latest bias: `-2.078` ms
- FIFO-5 Mean bias: `0.357` ms
- FIFO-5 Median bias: `-130.845` ms
- Rolling-leader regret mean: `125.296` ms
- Rolling-leader decision changes: `70`
- Rolling-leader final policy: `fifo5_median`
- Drift adaptation lag to FIFO-5 Median: `1` observations

## Drift Split
- Calibration host static MAE: `13.023` ms
- Calibration host FIFO-5 Median MAE: `47.917` ms
- Drift host static MAE: `1228.744` ms
- Drift host Latest MAE: `1116.251` ms
- Drift host FIFO-5 Median MAE: `802.298` ms

## Sample Depth
- Depth `0` FIFO-5 Median MAE: `623.766` ms, Latest MAE: `623.766` ms
- Depth `1` FIFO-5 Median MAE: `192.829` ms, Latest MAE: `192.829` ms
- Depth `2` FIFO-5 Median MAE: `96.083` ms, Latest MAE: `18.263` ms
- Depth `3` FIFO-5 Median MAE: `167.973` ms, Latest MAE: `167.967` ms
- Depth `4` FIFO-5 Median MAE: `101.924` ms, Latest MAE: `186.833` ms
- Depth `5+` FIFO-5 Median MAE: `346.068` ms, Latest MAE: `459.452` ms

## Validation Criteria
- Static fallback available for every observation: **Pass**
- Online windows kept per environment and not mixed across hosts: **Pass**
- FIFO-5 Median beat Static overall: **True**
- FIFO-5 Median beat Latest overall: **True**
- FIFO-5 Median was the recommended final policy: **True**

## Notes
- Fine-grained action windows were preserved, but sparse actions fell back to resource-kind windows before falling back to offline priors.
- The drifted environment benefited most from FIFO-5 Median because it damped noisy spikes while still tracking the new host.
- The calibration host remained comparatively stable, so the offline prior stayed competitive there.

## Generated Files
- `offline_costs.json`
- `online_windows.json`
- `static_predictions.csv`
- `latest_predictions.csv`
- `fifo5_mean_predictions.csv`
- `fifo5_median_predictions.csv`
- `scheduler_regret.csv`
- `phase7_summary.md`
- `phase7_summary.json`

## Phase Decision
Phase 7 is **passed_with_constraints**.
