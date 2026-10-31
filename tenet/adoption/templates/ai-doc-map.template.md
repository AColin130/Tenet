# AI 文档地图（模板）

> **复制到业务仓** `docs/ai-doc-map.md`（或 `docs/engineering/doc-map.md`）。**不要** 放在 `tenet/`。  
> 改代码/写设计前，AI 须在回复中 **点名本表一行** 的路径；**无行则先补 doc 再改**（Tier 2 + PR 可审）。

## 使用规则

1. 每行 = **一类问题** → **唯一 SSOT 文件**（一篇为准，避免双写）。  
2. 长文只在 `docs/`；Cursor `.mdc` **只链路径，不粘贴摘要**（见 [`../adoption/cursor-rules-example/README.md`](../adoption/cursor-rules-example/README.md)）。  
3. 与 [`baseline.md`](baseline.md)、[`adr/`](adr/) 冲突时 — **ADR/baseline 优先**，本表随之更新。

---

## Map（请按项目填写）

| 问题域 / 触发条件 | SSOT 路径 | 备注 |
|-------------------|-----------|------|
| 例：构建与预设 | `docs/…` 或 根 AGENTS.md §本地事实 | |
| 例：测试与验收命令 | `docs/testing.md` | |
| 例：模块 A 边界 | `docs/adr/0001-….md` | |
| 例：术语消歧 | `docs/GLOSSARY.md` | 可选 |
| （增行） | | |

---

## AI 回复格式（Tier 2）

```text
SSOT: docs/ai-doc-map.md → <上表某行路径>
（然后才给步骤/补丁）
```

---

## 相关

- Tenet [`project-vs-tenet.md`](../adoption/project-vs-tenet.md)  
- [`governance-tier-template.md`](../collaboration/governance-tier-template.md)
