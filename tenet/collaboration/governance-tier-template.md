# 治理分层模板（Tier 0 / 1 / 2）

**用途**：业务仓在 **G1 baseline** 或 `docs/governance.md` 中 **勾选**「约束落在哪一层」。Tenet **不** 替团队填具体规则（无 CAM/Qt/文件行数等）。

| Tier | 谁拦 | 典型手段 | 填什么 |
|------|------|----------|--------|
| **0** | **CI / 自动化** | 构建失败、lint、license 扫描、必要测试 | 命令、workflow 名（业务仓自建） |
| **1** | **人 Review** | PR checklist、CODEOWNERS、双人眼 | Review 清单项 |
| **2** | **Agent / 流程** | `tenet/AGENTS`、停步、**改代码前 cite SSOT 一行** | 行为约定；**人审 AI 时查 cite** |

---

## 填写表（复制到 `docs/governance.md`）

```markdown
# Governance（Tier）

> 与 docs/baseline.md §6 质量门禁一致。Tenet 模板：tenet/collaboration/governance-tier-template.md

## Tier 0 — CI 必须拦

| 规则 | 实现 |
|------|------|
| 例：Debug 构建通过 | `cmake --build …` |
| 例：关键 ctest | `ctest …` |
| （按项目增删） | |

## Tier 1 — Review 必须拦

| 规则 | 实现 |
|------|------|
| 例：DoD 清单 | code-review.md |
| 例：动 API 须 ADR | G2 |

## Tier 2 — Agent / 流程（Review 抽查 AI 是否遵守）

| 规则 | 实现 |
|------|------|
| 改代码前回复 **ai-doc-map 一行** | docs/ai-doc-map.md |
| 不过 G1 不批量搭架 | tenet/AGENTS.md |
| Delivery 停步 | stage-feedback |
```

---

## 与 Tenet 的关系

- **关口**（G0/G1/G2）= **决策** 是否允许做。  
- **Tier** = **同一条约束** 落在 CI、人眼、还是 Agent 自觉（+ 人抽查）。  
- 详见 [`../adoption/for-leads.md`](../adoption/for-leads.md)、[`../process/delivery/definition-of-done.md`](../process/delivery/definition-of-done.md)。

---

文档 v1.4 · Tenet collaboration（模板）
