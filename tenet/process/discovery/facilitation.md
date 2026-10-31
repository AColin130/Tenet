# Discovery / 教练引导（Facilitation）

本文档是 Tenet **教练层**：**怎么问、何时停、怎么选**。  
**裁判层** 仍是 [`exit-criteria.md`](exit-criteria.md)、[`../gates/G0-charter.md`](../gates/G0-charter.md)、[`../gates/G1-baseline.md`](../gates/G1-baseline.md) 与 [`../../AGENTS.md`](../../AGENTS.md)。

---

## AI 回复结构（默认）

避免用户收到长文后不知道下一步。每次回复优先：

1. **结论**（1～2 句）：当前阶段 + 能不能做 requested 动作  
2. **你要做的一步**：粘贴 [`../prompts/`](../prompts/README.md) 中 **一个** 模板或 **一道** ABCD 题  
3. **展开**（可选）：仅当用户要细节时再写长段  

详见 [`../../collaboration/ai-collaboration.md`](../../collaboration/ai-collaboration.md)。

---

## 阶段停步协议（强制）

完成下列事件后，AI **必须** 发出 [`../prompts/stage-feedback.md`](../prompts/stage-feedback.md) 中 **对应反馈块**（可略改措辞，**四问结构保留**），并 **停止** 以下行为直到用户明确回复：

| 事件 | 停步后禁止（直到用户回复） |
|------|----------------------------|
| G0 文档写入且标为通过 | 进入 G1、批量 CMake/模块树 |
| Discovery 一轮结束或 exit 项齐 | 宣称 G1 已通过、正式基线落盘 |
| G1 / baseline 标为通过 | 开始下一 Delivery 项（若用户未指定） |
| Delivery **单项** 验收完成 | 自动开始下一项或大改结构 |

**用户回复视为继续的信号**，例如：「进入 Discovery」「申请 G1」「开始 Delivery」「下一项：___」。

若用户说「继续」但 **未回答反馈问句**，AI 应 **追问一句** 确认（如「G0 边界是否还有修改？」），仍 **不** 越关口。

---

## 引导用户发什么（模板入口）

| 用户意图 | 给用户的模板 |
|----------|----------------|
| 刚嵌入 Tenet / 新项目 | [`../prompts/g0-start.md`](../prompts/g0-start.md) |
| Discovery 推进 | [`../prompts/discovery-sync.md`](../prompts/discovery-sync.md) |
| 准备基线 | [`../prompts/g1-request.md`](../prompts/g1-request.md) |
| 做一项交付 | [`../prompts/delivery-item.md`](../prompts/delivery-item.md) |
| 阶段结束复盘 | [`../prompts/stage-feedback.md`](../prompts/stage-feedback.md) |

AI 在用户 **不知如何开口** 时，应 **直接贴对应模板**（不是只给链接），并说明「复制后改方括号」。

---

## 分叉选项卡（ABCD）

在 **未过 G1 的架构决策** 或 **baseline 中必须二选一** 时，优先用选项题，最后一项固定 **D. 其他（请说明）**。

### 1 · Tenet 如何引入业务仓

- **A.** git submodule（`tenet/` 指向上游）  
- **B.** git subtree / vendor 拷贝（少依赖 submodule 习惯）  
- **C.** 仅拷贝 `tenet/` 目录，手动同步  
- **D.** 其他：___  

→ 结论写入 G0 charter 第 7 节。

### 2 · Delivery 节奏（G1 基线中择一）

- **A.** Scrum（建议迭代 2～4 周，固定 Review）  
- **B.** Kanban（WIP 限制，无固定 Sprint）  
- **C.** 先 Kanban 稳定后再 Scrum（写进 baseline 阶段说明）  
- **D.** 其他：___  

### 3 · 当前是否需要 disposable spike

- **A.** 不需要，只写文档/ADR  
- **B.** 需要，验证：___ ，目录/spike 名：___  
- **C.** 已有 spike，待结论后删除  
- **D.** 其他：___  

### 4 · 想法是否改变 G0 范围

- **A.** 否，记 backlog 即可  
- **B.** 是，要改 charter / 非目标  
- **C.** 不确定，先 Discovery 调研  
- **D.** 其他：___  

**B** 选中 → 回 G0 修订，**不** 直接改代码当 Delivery。

### 5 · 是否扩 scope / 换工具链

- **A.** 否，在 baseline 内 Delivery  
- **B.** 是，需要新 ADR（工具链/模块/集成）  
- **C.** 是，且可能改 G0 非目标  
- **D.** 其他：___  

**B/C** → ADR + [`../gates/G2-change.md`](../gates/G2-change.md)（及必要时 G0）。

---

## 与 Grill 的关系

- **Tenet 默认**：停步 + 模板 + ABCD，**不是** 对抗式盘问。  
- **Grill**（或同类）：用户 **可选** 触发，见 [`../prompts/stage-feedback.md`](../prompts/stage-feedback.md) 末尾；用于压测方案，**不替代** G0/G1/exit。

---

## 相关文档

- [`../../AGENTS.md`](../../AGENTS.md) — 停步强制  
- [`../prompts/README.md`](../prompts/README.md) — 模板索引  
- [`exit-criteria.md`](exit-criteria.md) — Discovery 出口  

---

文档 v1.1 · Tenet 教练层（与 OVERVIEW 版本一致）
