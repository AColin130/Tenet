# Cursor 规则范例（嵌入 Tenet 的业务仓）

**不含** 任何 WeCarver/CAM/UI 业务 glob。仅演示 **结构**。

## 原则

| 原则 | 说明 |
|------|------|
| **流程 SSOT** | 只认 `./tenet/AGENTS.md`；`.mdc` **不** 重写 Tenet 流程 |
| **单路由** | 仅 **一个** `alwaysApply: true` 的路由规则 |
| **懒加载** | 其余 `.mdc` 用 `globs` 匹配路径时再读 |
| **不双写** | `.mdc` 只链 `docs/` 路径；长文在 doc |

## 建议文件布局

```text
.cursor/rules/
  tenet-router.mdc      # alwaysApply: true
  docs-engineering.mdc  # globs: docs/**, AGENTS.md
  src-cpp.mdc           # globs: src/**, *.cpp, CMakeLists.txt
```

## 示例：`tenet-router.mdc`

```yaml
---
description: Route AI to Tenet SSOT and project glue
alwaysApply: true
---
Before any task: read ./tenet/AGENTS.md and ./AGENTS.md (glue).
Process authority is tenet/AGENTS.md only — do not invent a second process.
Before code edits: cite one row from ./docs/ai-doc-map.md in your reply.
Do not write project backlog/charter into ./tenet/.
```

## 示例：`docs-engineering.mdc`

```yaml
---
description: When editing docs, use doc-map SSOT
globs: docs/**,AGENTS.md,llms.txt
alwaysApply: false
---
When this rule applies: open docs/ai-doc-map.md and cite the matching SSOT path.
Do not paste long SSOT content here — link only.
```

## 示例：`src-cpp.mdc`

```yaml
---
description: When editing C++ sources
globs: src/**,include/**,CMakeLists.txt,cmake/**
alwaysApply: false
---
Cite docs/ai-doc-map.md row for build/test/API before changes.
Follow docs/baseline.md and accepted ADRs; structural change → G2 + ADR.
After edits: run acceptance commands from testing SSOT (doc-map row).
```

## 与 Tenet 官方仓

Tenet 官方仓 **可以没有** `.cursor/rules`；本目录仅供 **业务仓** 复制思路。

---

见 [`../integration-backlog.md`](../integration-backlog.md) P3。
