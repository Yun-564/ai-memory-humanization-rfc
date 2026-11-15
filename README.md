<div align="center">

# 🧠 AI 记忆系统"类人化"改造提案（RFC）

**让 AI 的长时记忆从"档案室"走向"类人记忆"：会遗忘、会联想、会归纳、会长大——同时保留机器的精确、可追溯与可回滚。**

[![Status: RFC 讨论中](https://img.shields.io/badge/status-RFC_讨论中-orange)]()
[![Lang: 中文](https://img.shields.io/badge/lang-中文-blue)]()
[![License](https://img.shields.io/badge/license-MIT-green)](./LICENSE)

> 📢 **本提案正在公开征集意见。** 欢迎在 Discussions 或 Issues 中对任何一条改造提出看法、质疑、经验或改进建议。
> 完整设计见 [docs/RFC-001.md](docs/RFC-001.md)。

</div>

---

## TL;DR

| # | 改造 | 一句话 | 难度 |
|---|---|---|---|
| 1 | 渐变遗忘 | 记忆按「重要度 × 时间衰减 + 提取强化」连续淡化，取代「保留/删除」二选一 | 低 |
| 2 | 语义联想检索 | 向量嵌入 + 混合检索，让记忆"自己浮现"而不是被关键词"查"出来 | 中 |
| 3 | 自动归纳巩固 | 空闲时把多条相似记忆聚类归纳成"高层规律"，细节分层保留 | 中高 |
| 4 | 再巩固带追溯 | 仅在冲突时改写，且以"组件级改动点"追加而非覆盖，可审计可回滚 | 中 |
| 5 | 记忆改变自身 | 行为层走 persona 蒸馏近路；能力层（改权重）为研究前沿，谨慎对待 | 研究级 |

**总体原则**：学习人类的遗忘与联想；保留机器的精确与追溯；不模仿人类的虚构与情绪染色。

**架构总纲**：人脑的互补学习系统（CLS）——「细胞化的海马」（外部记忆库，改 A 不伤 B）+「分布式慢改的皮层」（冻结基座 + 慢速蒸馏）。

---

## 目录

- [动机](docs/RFC-001.md#动机)：AI 记忆的五个"不像人"的问题
- [详细设计](docs/RFC-001.md#详细设计)：五项改造逐一展开（含神经科学依据与工程方案）
- [实施路线图](docs/RFC-001.md#实施路线图)
- [风险与取舍](docs/RFC-001.md#风险与取舍)
- [备选方案](docs/RFC-001.md#备选方案)
- [开放问题（求意见）](docs/RFC-001.md#开放问题求意见)
- [参考文献](docs/RFC-001.md#参考文献)

## 如何参与讨论

1. **Discussions**：到仓库 Discussions 的 💡 Ideas 板块发言（首选）；
2. **Issues**：新建 issue 参与逐条讨论；
3. **Pull Request**：直接对文档提交修改建议。

每一条有价值的意见都会进入讨论记录，被采纳的将更新进 RFC。

## English Summary

This RFC proposes five reforms to make AI long-term memory more human-like:

1. **Graded forgetting** — activation decay (importance × e^(-t/τ) + retrieval boost) instead of binary keep/delete;
2. **Associative recall** — hybrid embedding + keyword retrieval, so memories surface on their own;
3. **Automatic consolidation** — clustering similar memories into schemas with layered detail (rule / exemplar / exceptions / notes);
4. **Reconsolidation with traceability** — conflict-triggered updates that append component-level "change points" instead of overwriting, fully auditable and rollbackable;
5. **Experience-driven behavior change** — persona distillation as the near-term path; weight-level continual learning treated as research frontier.

The guiding principle: adopt human forgetting and association; keep machine precision and traceability; never fabricate. The architecture follows the brain's complementary learning systems: a cellular hippocampus (external memory) + a slowly-updating cortex (frozen base model + distillation).
