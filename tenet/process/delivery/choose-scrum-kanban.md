# 选择 Scrum 还是 Kanban

G1 基线中 **必须记录** Delivery 方式（二选一为主；混合须写清规则）。  
Tenet **不替团队选**；用下面 **ABCD** 快速定稿，结论写入 `docs/baseline.md` 第 5 节。

---

## 选项卡（复制给 AI 或直接回复）

**你更适合哪种 Delivery 节奏？**

- **A. Scrum** — 2～4 周迭代、固定 Sprint Review、backlog 按迭代承诺  
- **B. Kanban** — 持续流入、WIP 上限、无固定 Sprint 编号  
- **C. 先 B 后 A** — 例如：稳定期 Kanban，功能期切 Scrum（写清切换条件）  
- **D. 其他** — 说明：___  

选定后让 AI 把 **迭代长度 / WIP / Review 约定** 写进 baseline，**不要** 只口头说说。

---

## 对照表

| | Scrum | Kanban |
|---|--------|--------|
| **适合** | 产品功能块、要对外演示节奏 | 缺陷、运维、小改、流量波动 |
| **承诺** | 迭代内 PBI 集合 | 单卡流动，WIP 限制 |
| **AI 注意** | 不虚构 Sprint 号（除非项目已定义） | 不强行套 Sprint Planning |
| **DoD** | 项在 Review 前满足 [`definition-of-done.md`](definition-of-done.md) | 进「完成」列前满足 DoD |
| **Tenet 模板** | [`../prompts/delivery-item.md`](../prompts/delivery-item.md) 可写「本迭代第 N 项」 | 同一模板，不写 Sprint 亦可 |

小团队 **≤5 人** 常选 **B** 或 **短 Scrum（1～2 周）**；参照 20+ 人习惯时 **Scrum + 集成演示** 更常见。

---

## 与 facilitation 的关系

Tenet 引入方式等其它 ABCD 见 [`../discovery/facilitation.md`](../discovery/facilitation.md)。  
本文件 **只** 负责 Delivery 节奏选型。

---

## 相关文档

- [`definition-of-done.md`](definition-of-done.md)
- [`../gates/G1-baseline.md`](../gates/G1-baseline.md)
- [`../OVERVIEW.md`](../OVERVIEW.md)

---

文档 v1.2 · Tenet delivery
