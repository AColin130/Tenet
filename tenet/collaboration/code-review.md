# 代码评审（Code Review）

Review 是 **DoD 第 4 条** 的落地方式。Tenet 不绑定 GitHub/GitLab UI；下列为 **语义**，写入用户 **baseline §6** 时可增删。

---

## 目标

- 与 **baseline / ADR** 一致，不 silent 扩大 scope  
- 可维护、可构建、可验收  
- AI 生成代码同样 **必须** 被 Review（或等价自检）

---

## 最小 Review（默认）

| 步骤 | 内容 |
|------|------|
| **作者自检** | 对照 DoD 2–3：验收命令跑过；无 debug 残留、无密钥 |
| **Diff 阅读** | 另一 **角色**（见 [`roles.md`](roles.md)）或作者 **隔日再审**（1 人团队） |
| **关口** | 结构性变更 → 已有 **G2/ADR**；否则 **拒绝合并** |
| **AI 辅助** | Reviewer 可 @ `tenet/AGENTS.md` 问：「是否违反 baseline 非目标？」 |

---

## Review 清单（可复制）

```text
【Review 清单】
- [ ] 与 docs/baseline.md 及 ADR 一致
- [ ] AI/作者已 cite docs/ai-doc-map.md 一行（若已启用）
- [ ] 验收命令/测试已跑（注明命令）
- [ ] 无 G0 禁止的依赖/license
- [ ] 非 disposable spike 残留
- [ ] 需 ADR 的变更已 ADR 已接受
- [ ] 合并前门禁（baseline §6）满足
- [ ] PR 描述含 SSOT 路径（见 templates/pull_request_template.business.md）
```

## 新符号 / API（不维护全量清单）

- 新增对外符号前：**grep 仓库** 是否已有；更新 **doc-map 所指** API/模块 doc 或 ADR。  
- 术语消歧用 **`docs/GLOSSARY.md`**（可选），与 map 一行分工。

---

## 与 AI 协作

- **禁止** AI 自评「无需 Review」而直接宣称 Delivery 完成。  
- 单人项目：自检清单 + **Delivery 停步** 用户确认 = 最小 Review。  
- 多人：**至少 1 人非作者** 看过 diff 再合并。

---

## 相关文档

- [`../process/delivery/definition-of-done.md`](../process/delivery/definition-of-done.md)
- [`roles.md`](roles.md)
- [`ai-collaboration.md`](ai-collaboration.md)

---

文档 v1.4 · Tenet collaboration
