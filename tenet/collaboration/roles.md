# 协作角色（Roles）

Tenet 用 **角色** 描述关口谁签字、谁决策——**不要求** 对应公司职级或头衔。  
小团队可 **一人兼多角**；20+ 人时可拆分。角色定义写在 **用户项目** G0 charter §2 或 `docs/roles.md`（Tenet 不预置该文件）。

---

## 核心角色

| 角色 | 职责 | 关口 |
|------|------|------|
| **产品/业务代表** | 价值、范围、优先级；确认非目标 | G0 签字；scope 变更 |
| **技术负责人（Tech Lead）** | 架构原则、ADR、G1/G2 通过；Discovery 出口确认 | G1、G2；exit-criteria 确认 |
| **交付负责人** | Scrum PO 或 Kanban 列负责人；backlog 顺序 | Delivery 计划 |
| **集成/构建负责人**（可兼） | 构建 SSOT、工具链 ADR、合并门禁 | G2 中工具链类变更 |
| **Tenet 包维护者**（业务仓内） | 同步 `tenet/` 拷贝或 submodule；胶水 AGENTS 不丢 | 非 Tenet 官方仓维护者 |

---

## 关口与签字（最小）

| 关口 | 最少参与 | 记录位置 |
|------|----------|----------|
| **G0** | 业务 + 技术各 1 角色（可同人） | `docs/charter.md` §8 |
| **Discovery 出口** | 技术负责人 | `docs/discovery/EXIT.md` |
| **G1** | 技术 + 业务或业务委托 | `docs/baseline.md` §7 |
| **G2** | 同 G1 或更轻（baseline 约定） | `docs/gates/G2*.md` |
| **Delivery 完成** | 作者 + Reviewer（见 code-review） | DoD + 停步反馈 |

---

## 团队规模裁剪

| 规模 | 建议 |
|------|------|
| **1 人 + AI** | 全部角色同人；仍 **落盘** G0/G1/ADR，便于以后加人 |
| **2–5 人** | Tech Lead + 轮流 Review；G0/G1 口头对齐也要写进文档 |
| **20+ 人** | 固定 RTE/集成负责人；G2 必须书面；Review 不省略 |

裁剪规则详见 [`../adoption/for-leads.md`](../adoption/for-leads.md)。

---

## AI 行为

- 不得 **伪造** 签字或「已通过 G1」；须指向仓库内 **状态字段**。  
- 用户未定义角色时 → 引导在 G0 §2 填 **角色名**（可写「本人兼全部」）。

---

## 相关文档

- [`../process/gates/G0-charter.md`](../process/gates/G0-charter.md)
- [`code-review.md`](code-review.md)
- [`../adoption/for-leads.md`](../adoption/for-leads.md)

---

文档 v1.4 · Tenet collaboration
