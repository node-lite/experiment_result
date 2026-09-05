# NodeLite 七阶段实验最终报告

生成时间：2026-09-06

## 总览

这份报告汇总了 `CODEX_NODELITE_7_PHASE_EXPERIMENT_PLAN_CN.md` 里的七个 phase 的结果。

当前结论很清楚：

- Phase 1 到 Phase 7 的主线已经跑通。
- Phase 1 仍然是 `partial`，没有达到严格意义上的完全通过。
- Phase 2 到 Phase 7 都是 `passed_with_constraints`。
- 最终在线窗口策略推荐 `FIFO-5 Median`。
- 这套结果仍然是以 replay / derived validation 为主，Docker warm-image baseline 和 full ablation 在当前仓库快照里没有独立测量，因此不能在这个报告里被写成已完成结论。

## 七个 Phase 汇总

| Phase | 名称 | 结论 | 关键结果 |
|---|---|---|---|
| Phase 1 | CTDP Dependency Preparation Validation | `partial` | 64 / 64 profiles 覆盖；dedup ratio `0.6721`；first-run network bytes `9.23 GB`；second-run network bytes `213.8 MB`；targeted rerun 修复了 21 个外部 artifact miss，但严格 G2 验证仍有未解决项 |
| Phase 2 | Object / Action Latency Profiling | `passed_with_constraints` | 8,589 条原始 observation；316 个 benchmark 全覆盖；64 个 profile 的成本库和对象/动作延迟数据可用于后续 phase |
| Phase 3 | Resource Reuse Validation | `passed_with_constraints` | 64-profile 固定序列下，总 Fresh `8,028,246.815 ms`，总 Reuse `144,898.131 ms`，节省 `7,883,348.685 ms`，speedup `55.41x`，reuse hit rate `98.99%` |
| Phase 4 | Transition Cost Model Validation | `passed_with_constraints` | 4,032 / 4,032 directed pairs 可预测；MAE `19,744.347 ms`；Pearson `0.9975`；Spearman `0.9946` |
| Phase 5 | Resource-Aware Scheduling | `passed_with_constraints` | NodeLite 比 FIFO 少 `639,060.115 ms`；但比 Similarity greedy 多 `425,534.375 ms`；决策开销仅 `0.607 ms` 总计 |
| Phase 6 | Seed Priority Queue Validation | `passed_with_constraints` | Weighted Reach 比 Fastest 好，但在这份 replay 里不如 Degree；starvation probe 通过，age bonus 可以把长期等待 seed 拉回前面 |
| Phase 7 | Online Sliding-Window Adaptation | `passed_with_constraints` | 推荐 `FIFO-5 Median`；overall MAE `343.644 ms`，优于 Static `489.601 ms` 和 Latest `454.552 ms`；drift host 上也更稳 |

## 关键发现

### 1. CTDP 的价值已经被证明，但 phase 1 还不是严格全通过

Phase 1 的核心信号是正向的：

- 去重比例达到 `0.6721`
- 第二次运行网络流量显著下降到 `213.8 MB`
- targeted rerun 把 21 个外部 artifact miss 修掉了

但它仍然保留严格计划里的未完成项，所以最后只能记为 `partial`，不能写成完全通过。

### 2. Resource Reuse 的收益非常大

Phase 3 给出的结论很强：

- Fresh `8.028 s` 级别总开销
- Reuse 只有 `0.145 s` 级别
- 总体节省接近 `7.88 s` 级别
- reuse hit rate 接近 `99%`

这说明在固定 64-profile 序列里，warm state 复用不是小修小补，而是决定量级的收益来源。

### 3. Cost Model 足够可信，能支撑后续 scheduler 和 seed queue

Phase 4 的 pair 预测几乎覆盖完全：

- 4,032 / 4,032 directed pairs 都能预测
- 相关性很高，说明对象级 cost 具备很强的排序和比较能力

这使得后面的 Phase 5 / 6 / 7 都有了可用的基础，而不是在不稳的成本表上空转。

### 4. Scheduler 确实有收益，但不是“万能第一名”

Phase 5 证明了 NodeLite scheduling 不是白忙：

- 对 FIFO 有明确收益
- 决策开销极小

但它在这份 replay 里仍然输给 Similarity greedy，说明 cost-aware scheduling 有价值，但还没有在当前任务分布上全面压过相似性启发式。

### 5. Seed Queue 是一个“约束下有效”的 fallback 方案

Phase 6 的结论比较克制，也比较真实：

- Weighted Reach 不是全局最优
- 但它确实比 Fastest cold start 更合理
- starvation probe 证明 age bonus 能防止长期饿死

所以它更像是一个可靠的 fallback policy，而不是在所有 replay 状态下都最优的 policy。

### 6. Online FIFO 的最终推荐是 FIFO-5 Median

Phase 7 的结果最明确：

- `FIFO-5 Median` 的 overall MAE 最低
- `FIFO-5 Median` 的 P95 也最好
- drift 环境下它比 Static 和 Latest 更稳
- rolling leader 最终也收敛到 `fifo5_median`

这意味着在线适应不是简单地追最近一个样本，而是要保留一个短窗口、用中位数压噪声。

## 最终回答

### CTDP 单独贡献多少？

从 Phase 1 看，CTDP 对依赖准备和重复下载的帮助是明确的：

- 去重比例 `0.6721`
- second-run network bytes 从 `9.23 GB` 下降到 `213.8 MB`
- targeted rerun 把 21 个 external artifact miss 修复掉

但严格讲，Phase 1 仍然是 `partial`，所以它的贡献应该写成“已证明有效，但严格全量验证未完全闭环”。

### Resource Reuse 额外贡献多少？

Phase 3 里，Resource Reuse 带来的额外收益非常大：

- 总节省 `7,883,348.685 ms`
- speedup `55.41x`
- reuse hit rate `98.99%`

这是整个七阶段里最有量级感的结论之一。

### Scheduler 再额外贡献多少？

Phase 5 里，NodeLite cost greedy 相比 FIFO：

- 节省 `639,060.115 ms`
- speedup `1.072x`

但它仍然比 Similarity greedy 差 `425,534.375 ms`，所以 scheduler 的收益是成立的，但当前实现还不是绝对最强。

### Online FIFO 是否继续提升 prediction / scheduling？

是，至少在 Phase 7 的这个 replay 里是这样。

- `FIFO-5 Median` 是最优的在线窗口策略
- 它比 Static 和 Latest 都好
- 它在 drift 环境下也更稳

### 相对于 Docker warm-image baseline 最终怎么样？

当前仓库快照里没有独立的 Docker warm-image baseline 测量结果，所以这一项**不能在本报告里被当作已完成比较**。

换句话说：

- 七个 phase 的验证已经完成
- 但 Docker baseline / full ablation 这一条，当前只能记为后续补测项

## 结论

如果只看七个 phase 的链路，那么 NodeLite 这条路线是成立的：

- CTDP 证明了依赖准备和去重的基础收益
- Resource Reuse 把收益放大到数量级
- Cost Model 足够准，可以支撑排序和 fallback 决策
- Scheduler 和 Seed Queue 进一步优化任务顺序与 fallback seed
- Online FIFO 把运行期预测做得更稳

但如果按最终计划的完整定义来写，报告应该保留一个诚实的边界：

> 七个 phase 已完成，核心链路已验证；Docker warm-image baseline 与 full ablation 还没有在当前 artifact 中形成独立可比结果。

## 产物索引

- [phase1/ctdp/phase1/phase1_summary.md](/root/experiment_result/phase1/ctdp/phase1/phase1_summary.md)
- [phase2/phase2_summary.md](/root/experiment_result/phase2/phase2_summary.md)
- [phase3/phase3_summary.md](/root/experiment_result/phase3/phase3_summary.md)
- [phase4/phase4_summary.md](/root/experiment_result/phase4/phase4_summary.md)
- [phase5/phase5_summary.md](/root/experiment_result/phase5/phase5_summary.md)
- [phase6/phase6_summary.md](/root/experiment_result/phase6/phase6_summary.md)
- [phase7/phase7_summary.md](/root/experiment_result/phase7/phase7_summary.md)

