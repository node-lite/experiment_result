# Phase 2 实验结果

本目录保存 NodeLite Phase 2 的 object/action 延迟标定结果，以及针对首轮 `unmeasured_objects.json` 中 380 个真实 RepoProfile object 的补测结果。

## 结论

- 阶段状态：`passed_with_constraints`。
- Scheduler 相关的真实 object 共 384 个：207 个 `measured`、102 个 `blocked`、75 个 `manual_review`，当前没有隐式 `unmeasured` object。
- 本轮 exact workload 对 380 / 380 个目标完成了状态归档：203 个 `measured`、102 个 `blocked`、75 个 `manual_review`、0 个 `failed`。
- 合并后包含 8,589 条 raw observation、8,322 条 active observation 和 1,190 条 transition summary。
- 当前 exact calibration host 贡献 3,367 条 raw observation、3,170 条 active observation、454 条 transition summary 和 204 个 `direct_ms` object。
- `blocked`、`manual_review` 和 `unsupported` 只表示对象已被明确归类，不是延迟为零，也不能作为成功测量参与调度成本拟合。
- generic/synthetic benchmark 仍可作为校准证据，但不算某个真实 RepoProfile object 的 exact measurement。

## Exact 实测

本轮 exact workload 已实测 64 个 repo baseline、65 个 source overlay、31 个 dependency view、15 个 build cache、9 个 test-transform cache、5 个 native bundle 和 14 个 rootfs object。默认每个 action 执行 2 次 warmup 和 7 次 measurement；单次超过 30 秒的 action 按实验计划降为 5 次 measurement，并在 summary 中保留真实样本数。

完整的 median、P95、样本数、成功/失败数和环境 ID 见 `phase2_summary.md` 与 `exact_workload/object_action_summary.csv`。

## 约束

- 当前 exact calibration host 已具备 GitHub 网络、Docker、mount，以及 Node 18.19.1/20.19.1/22.23.2（ABI 109/115/127）；repo/source/rootfs 和三个 Node ABI 均已在本机实测。能力探测证据见 `exact_workload/capabilities.json`。
- 剩余 blocked 主要来自 CTDP CAS/native cache 缺少 lockfile 所引用的 tarball、Yarn offline mirror 缺件、项目 lockfile 与 manifest 不再满足 frozen install、项目 warmup/build/test 命令自身失败，以及 native object 的 dependency view 未能物化。
- 12 个 dependency view 保持 `manual_review`：其中 9 个目标 lock hash 与现有 CTDP snapshot 不一致，3 个 dependency root 已由 CTDP 判为 unsupported/manual review。为保持 exact 语义，不会静默替换 lock hash。
- `node_runtime:unknown`、`rootfs:unknown`、精确 PM 版本为 `unknown` 或 registry 中不存在的版本仍保持明确缺口；这类问题是输入 provenance/版本可获得性问题，不是当前主机缺少 Node 18/20/22 或 Docker。
- 两个 Playwright 项目的脚本会在每轮测试中执行无边界的全浏览器下载；为避免填满共享磁盘，本轮保留为 blocked，并记录真实 `Terminated` 证据。

## 环境隔离

本目录包含两台主机的观测：

| Environment ID | Host | CPU | Node | npm | 用途 |
|---|---|---:|---|---|---|
| `env:7a9cda66bc6b151a7886` | `hydu8x5090gpu` | 384 | `v22.23.2` | `10.9.8` | 原 Phase 2 benchmark |
| `env:0fd7b54e0a2a55d4208d` | `ecs-troy-d0b3` | 16 | ABI 109/115/127 exact runtimes | 按 profile exact PM | exact workload 补测 |

所有 observation 和 summary 都保留 `measurement_environment_id`。调度器必须从 `direct_ms_by_environment.json` 选择一个环境的窗口，不能跨主机平均 `direct_ms`。

## 文件索引

- `phase2_summary.md` / `phase2_summary.json`：阶段结论、覆盖率、关键 transition 和 exact 状态汇总。
- `unmeasured_objects.json`：384 个 scheduler-relevant object 的最终状态、原因和证据；文件名沿用首轮 gap report，内容已经是最终 accounted 状态。
- `object_action_observations.jsonl`：raw 合并观测，体积较大并由仓库 `.gitignore` 排除。
- `object_action_summary.csv` / `object_switch_matrix.csv`：按 active/latest observation 重建的 1,190 条 transition summary。
- `measurement_environments.json`：两套测量环境的完整描述与混用策略。
- `direct_ms_by_environment.json`：各环境独立 `direct_ms` 文件的索引。
- `exact_workload/`：380 个 exact 目标的状态、3,367 条 raw observation、3,170 条 active observation、进度、能力探测和当前主机 CostDB。
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
  --samples 7 \
  --retry-failed
python3 tools/export_phase2.py
```

不要为了普通 resume 删除 `out/exact-workload`：现有 `object_status.json` 同时保存原始 380 个目标集合。`--retry-failed` 仅重跑 `blocked`、`failed` 和 `unsupported`，`--force` 会重测全部目标；从完全空目录重建时，应先生成 exact merge 之前的 baseline gap manifest。
