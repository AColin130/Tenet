# AI 协作约定

与 [`../AGENTS.md`](../AGENTS.md)、[`../process/discovery/facilitation.md`](../process/discovery/facilitation.md) 一并使用。  
业务仓 **Tier / doc-map / llms** 模板见 [`../adoption/templates/`](../adoption/templates/README.md)。

---

## 默认回复格式

| 顺序 | 内容 | 上限建议 |
|------|------|----------|
| 1 | 当前 Tenet **阶段** + 本请求 **做或不做** | 2 句 |
| 2 | **SSOT 一行**（业务仓 `docs/ai-doc-map.md` 已启用时） | 1 行路径 |
| 3 | **一步**：模板 / ABCD | 1 块 |
| 4 | 细节 | 用户追问后再展开 |

**禁止** 默认用长篇教程代替「cite SSOT + 下一步」。

---

## 改代码前：问题 → 唯一 SSOT（业务仓 Tier 2）

若业务仓已有 [`docs/ai-doc-map.md`](../adoption/templates/ai-doc-map.template.md)（从模板复制）：

- 回复须含 **`SSOT: <路径>`**，且路径 **对应 map 表一行**。  
- **无行** → 先补 doc / ADR，**再** 改代码。  
- 人审 AI 时查：**是否 cite、是否与 baseline/ADR 一致**。

Tenet **不在 `tenet/` 内** 写业务 map 行。

---

## 读序封顶（~40）与懒加载

1. 业务根 `llms.txt`（硬约束短列表）→ 2. 胶水 `AGENTS.md` → 3. `tenet/AGENTS.md` → 4. **map 所指的一篇** SSOT。  
5. **不要** 一次加载全库 docs；Cursor 专题用 **glob `.mdc` 懒加载**（范例 [`../adoption/cursor-rules-example/`](../adoption/cursor-rules-example/README.md)）。

模板：[`llms.txt.template`](../adoption/templates/llms.txt.template)。

---

## 子 Agent / Task（Cursor 等）

- **子任务与主 Agent 同责**：产出也须 **cite SSOT 一行**（或说明 G0/G1 阶段禁止改码）。  
- **不得** 因「子 agent 做的」跳过停步、G2、DoD。

---

## User Skills（Grill、domain-modeling 等）

- **Skill 定义不进业务仓**（个人/全局），避免团队 Skill 版本分叉。  
- **结论进 repo**：ADR、`docs/`、backlog；Grill **可选**，见 [`../process/delivery/grill-doc-default.md`](../process/delivery/grill-doc-default.md) 与 facilitation 优先级。

---

## 多工具（Cursor、Claude Code、Copilot 等）

- 流程 **只认** `tenet/AGENTS.md`；`.mdc` **只路由**，不双写 Tenet 正文。  
- 业务仓根 `AGENTS.md`：**本地事实** + 指向 tenet +（可选）doc-map / llms 路径。

---

## 阶段停步 vs Delivery Grill+Doc

| 阶段 | 主导 |
|------|------|
| **G1 前** | facilitation **停步**；禁止批量搭架 |
| **Delivery** | 默认 **Grill+Doc**（可四条跳过）→ [`grill-doc-default.md`](../process/delivery/grill-doc-default.md) |

**不得** 用 Grill 替代 G1。

---

## 用户不知道说什么时

1. 判断阶段。  
2. 贴 [`../process/prompts/`](../process/prompts/README.md) **一个** 模板。

---

## 可选压测

[`stage-feedback`](../process/prompts/stage-feedback.md) 末尾 Grill 块；非 G0/G1 默认。

---

## 相关

- [`governance-tier-template.md`](governance-tier-template.md)  
- [`../adoption/integration-backlog.md`](../adoption/integration-backlog.md)  
- [`../adoption/project-vs-tenet.md`](../adoption/project-vs-tenet.md)

---

文档 v1.5 · Tenet collaboration
