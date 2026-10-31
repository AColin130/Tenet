# Tenet 采纳待办（WeCarver 对照 · 仅元层/模板）

> **原则**：只提供 **行为约定 + 空表模板 + adoption 范例**；**不写** WeCarver/CAM/UI/OCL 等业务红线。  
> **状态**：`[x]` = 已写入 Tenet v1.5 文档集（见 [`templates/README.md`](templates/README.md)）。

| ID | 项 | 状态 | 产出物 |
|----|-----|------|--------|
| P1-1 | Tier 0/1/2 治理表 | [x] | [`governance-tier-template.md`](../collaboration/governance-tier-template.md) |
| P1-2 | ai-doc-map 空表 | [x] | [`templates/ai-doc-map.template.md`](templates/ai-doc-map.template.md) |
| P1-3 | 子 Agent 同责 cite SSOT | [x] | [`ai-collaboration.md`](../collaboration/ai-collaboration.md) |
| P1-4 | Skills 不进仓 | [x] | `ai-collaboration.md` + [`grill-doc-default.md`](../process/delivery/grill-doc-default.md) |
| P2-1 | llms.txt 模板 + 官方仓极简 | [x] | [`templates/llms.txt.template`](templates/llms.txt.template)、根 [`llms.txt`](../../llms.txt) |
| P2-2 | 读序封顶 ~40 | [x] | `ai-collaboration.md` |
| P3-1 | Cursor 路由 + lazy mdc | [x] | [`cursor-rules-example/`](cursor-rules-example/README.md) |
| P3-2 | .mdc 不双写 SSOT | [x] | 同上 |
| P4-1 | Delivery Grill+Doc + 四条跳过 | [x] | [`grill-doc-default.md`](../process/delivery/grill-doc-default.md) |
| P5-1 | mistake registry 模板 | [x] | [`templates/mistake-registry.template.md`](templates/mistake-registry.template.md) |
| P5-2 | 双 journal 模板 | [x] | [`templates/journal.template.md`](templates/journal.template.md) |
| P6-1 | PR 模板 SSOT 一行 | [x] | [`templates/pull_request_template.business.md`](templates/pull_request_template.business.md) |
| P6-2 | 新符号先 grep | [x] | `code-review.md`、`engineering-standards.md` |
| P6-3 | testing SSOT 提示 | [x] | `engineering-standards.md` |
| P7-1 | 胶水 AGENTS / project-vs-tenet | [x] | `project-vs-tenet.md`、`OVERVIEW` 嵌入节 |

## 整合风险（已写入相关 doc）

- 双 SSOT → 仅空表模板  
- Grill vs 停步 → facilitation + grill-doc-default 优先级表  
- Tier 2 人审 → PR 模板 + code-review cite  
- .mdc 分叉 → cursor-rules-example + ai-collaboration  

---

文档 v1.5 · 本待办 **closed**；新想法请开 GitHub Issue。
