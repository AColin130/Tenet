# Delivery 默认：Grill + Doc（G1 之后）

**不替代** G0 / Discovery / G1 的 **facilitation 停步** 与关口。  
**仅 Delivery 轨**：新需求默认 **先澄清/压测 + 更新 SSOT**，再写码。

---

## 默认节奏（G1 已通过）

1. **Grill（可选 Skill）**：挑刺假设、边界、遗漏（个人/全局 Skill，**不进仓库**）。  
2. **Doc**：更新 `docs/ai-doc-map` 所指 SSOT 或 ADR/backlog **一行**。  
3. **Delivery 项**：用 [`../prompts/delivery-item.md`](../prompts/delivery-item.md) 开工。  
4. **完成**：DoD + [`stage-feedback`](../prompts/stage-feedback.md)。

Grill 与 Tenet 可选块见 [`../prompts/stage-feedback.md`](../prompts/stage-feedback.md) 末尾。

---

## 四条可跳过（须 **同时** 满足才可跳过 Grill+Doc）

| # | 条件 |
|---|------|
| 1 | 变更 **不** 扩大 G0 非目标、**不** 触发 G2 |
| 2 | **已有 accepted SSOT**（map 一行 + 文档）**完全覆盖** 本项 |
| 3 | 用户 **明确**「按 SSOT X 直接做」 |
| 4 | 验收命令已在 baseline / testing SSOT 中写清 |

跳过时不做 Grill；仍须 **cite SSOT 路径** 再改代码。

---

## 与 facilitation 优先级

| 阶段 | 主导 |
|------|------|
| G0 / Discovery / G1 前 | **facilitation** 停步 + 禁止批量搭架 |
| Delivery | 本节 **Grill+Doc 默认** + 四条跳过 |

AI **不得** 用 Grill 绕过 G1。

---

文档 v1.4 · Tenet delivery
