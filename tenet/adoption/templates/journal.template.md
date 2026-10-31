# 双日志（模板）

> **业务仓** 可选；与 Tenet **关口文档**（charter/baseline）分工：**关口 = 决策**，journal = **操作史**。

## 分工

| 文件 | 何时写 | 何时入库 |
|------|--------|----------|
| `docs/journal/local.md` 或 `.local/journal.md`（gitignore 可选） | **每次** 改动/session 摘要 | 可选不入库 |
| `docs/changelog/unreleased.md` | **仅** commit / push / merge 前 | 入库 |

**禁止** 把 unreleased 当对话 dump；**禁止** 用 unreleased 替代 [`mistake-registry`](mistake-registry.template.md) 活表。

## local 条目（示例）

```markdown
## YYYY-MM-DD HH:MM
- 做了什么：
- SSOT 行：
- 下一步：
```

## unreleased 条目（示例）

```markdown
## [Unreleased]
### Changed
- （合并前写，与 commit 单语一致）
```

---

见 [`../integration-backlog.md`](../integration-backlog.md) P5-2。
