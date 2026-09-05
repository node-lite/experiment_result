# Phase 2 实验结果

本目录保存 NodeLite Phase 2 的 object/action 延迟标定结果，以及针对首轮 `unmeasured_objects.json` 中 380 个真实 RepoProfile object 的补测结果。

## 结论

- 阶段状态：`passed_with_constraints`。
- Scheduler 相关的真实 object 共 384 个：8 个 `measured`、363 个 `blocked`、13 个 `manual_review`，当前没有隐式 `unmeasured` object。
- 本轮 exact workload 对 380 / 380 个目标完成了状态归档：新增 4 个 exact dependency view 实测，363 个 blocked，13 个 manual review。
- 合并后包含 5,306 条 raw observation、5,236 条 active observation 和 748 条 transition summary。
- `blocked`、`manual_review` 和 `unsupported` 只表示对象已被明确归类，不是延迟为零，也不能作为成功测量参与调度成本拟合。
- generic/synthetic benchmark 仍可作为校准证据，但不算某个真实 RepoProfile object 的 exact measurement。

## Exact 实测

4 个新增 dependency view 都执行了 2 次 warmup，以及各 7 次 materialize、attach 和 dirty reset 采样，共产生 84 条成功 observation：

| Profile | Materialize median | Attach median | Reset median |
|---|---:|---:|---:|
| `foambubble__foam.2cac8162` | 5,856.184 ms | 0.575 ms | 0.024 ms |
| `jaredpalmer__formik.91475adb` | 5,837.947 ms | 0.263 ms | 0.027 ms |
| `redux-saga__redux-saga.a4ace10d` | 9,529.210 ms | 1.135 ms | 0.025 ms |
| `sveltejs__svelte.6c9717a9` | 1,802.468 ms | 0.062 ms | 0.024 ms |

完整的 P95、样本数和环境 ID 见 `phase2_summary.md` 与 `exact_workload/object_action_summary.csv`。

## 约束

- CTDP 当前保存依赖 manifest、lock snapshot、CAS 和 PM native cache，但不保存 64 个仓库的完整 exact commit checkout。因此 `repo_baseline`、`source_overlay`、`build_cache` 和 `test_transform_cache` 无法在没有源码快照时补测。
- 运行时 GitHub DNS 解析失败，网络补取源码未成功；原始探测证据保存在 `exact_workload/capabilities.json`。
- 当前主机没有 Docker/container runtime，`rootfs` transition 无法实测。
- 当前主机只提供 Node ABI 109；要求 ABI 115 或 127 的 object 没有被替代测量。
- exact PM 版本、lock hash 或 CTDP snapshot 不匹配时保持 blocked/manual-review，不用近似版本冒充 exact 数据。

## 环境隔离

本目录包含两台主机的观测：

| Environment ID | Host | CPU | Node | npm | 用途 |
|---|---|---:|---|---|---|
| `env:7a9cda66bc6b151a7886` | `hydu8x5090gpu` | 384 | `v22.23.2` | `10.9.8` | 原 Phase 2 benchmark |
| `env:0fd7b54e0a2a55d4208d` | `ecs-troy-d0b3` | 16 | `v18.19.1` | `9.2.0` | exact workload 补测 |

所有 observation 和 summary 都保留 `measurement_environment_id`。调度器必须从 `direct_ms_by_environment.json` 选择一个环境的窗口，不能跨主机平均 `direct_ms`。

## 文件索引

- `phase2_summary.md` / `phase2_summary.json`：阶段结论、覆盖率、关键 transition 和 exact 状态汇总。
- `unmeasured_objects.json`：384 个 scheduler-relevant object 的最终状态、原因和证据；文件名沿用首轮 gap report，内容已经是最终 accounted 状态。
- `object_action_observations.jsonl`：raw 合并观测，体积较大并由仓库 `.gitignore` 排除。
- `object_action_summary.csv` / `object_switch_matrix.csv`：按 active/latest observation 重建的 748 条 transition summary。
- `measurement_environments.json`：两套测量环境的完整描述与混用策略。
- `direct_ms_by_environment.json`：各环境独立 `direct_ms` 文件的索引。
- `exact_workload/`：380 个 exact 目标的状态、84 条原始成功观测、进度、能力探测和当前主机 CostDB。
- `reproduction.json`：运行命令、代码版本、协议参数、环境 ID 与关键产物 SHA-256。

## 恢复与导出

在保留 `/root/NodeLite-Schduler/out/exact-workload/object_status.json` 的情况下，下列命令会恢复原来的 380-object 目标集合并跳过已完成项：

```bash
cd /root/NodeLite-Schduler
./nodelite-bench \
  --ctdp-out /root/experiment_result/phase1/ctdp \
  run-exact-workload \
  --inventory /root/NodeLite-Schduler/out/inventory.json \
  --gaps /root/experiment_result/phase2/unmeasured_objects.json \
  --exact-out /root/NodeLite-Schduler/out/exact-workload \
  --warmups 2 \
  --samples 7
python3 tools/export_phase2.py
```

不要为了普通 resume 删除 `out/exact-workload`：现有 `object_status.json` 同时保存原始 380 个目标集合。使用 `--force` 会重测这些目标；从完全空目录重建时，应先生成 exact merge 之前的 baseline gap manifest。

