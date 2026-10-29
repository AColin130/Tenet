# Tenet — AI 与协作权威

本文件是 **Tenet 流程与 AI 行为** 的单一事实来源（SSOT）。  
Tenet 是 C++ 团队的 **规矩 + AI 引导** 元层包，**不是** 带固定架构的脚手架。

---

## 权威声明

- **流程、关口、Discovery/Delivery 边界、禁止项**：以本文件及 `process/` 下文档为准。
- **业务架构与工程形状**：由 **用户 + AI 在对话中** 选型并记录；Tenet **不提供** 默认 monorepo / exe / 库布局模板。
- 用户业务仓中若存在根 `AGENTS.md`：**流程以本文件为准**；根文件仅保留 **本项目事实**（构建入口、测试路径、CODEOWNERS 等）。冲突时 — **流程归 Tenet，本地事实归根文件**。

若你尚未完整阅读本文件，**停止** 批量生成代码、目录树或 CMake；先读 [`process/OVERVIEW.md`](process/OVERVIEW.md) 并判定当前阶段。

---

## 开始任务前

1. 阅读 [`process/OVERVIEW.md`](process/OVERVIEW.md)（权威链、双轨、关口）。
2. 判定 **当前阶段**：
   - **Discovery**：探索、对比、ADR 草案、spike；默认 **不** 正式落盘工程基线。
   - **G0 未过**：不得假设产品边界、许可证策略、发布目标（见 [`process/gates/G0-charter.md`](process/gates/G0-charter.md)）。
   - **G1 未过**：不得将讨论中的方案当作 **已批准基线** 批量写入仓库（见 [`process/gates/G1-baseline.md`](process/gates/G1-baseline.md)、[`process/discovery/exit-criteria.md`](process/discovery/exit-criteria.md)）。
   - **Delivery**：已过 G1；变更应对应 backlog / 看板项，并满足 DoD（DoD 细则 v2；v1 以 G1 与 exit-criteria 为底线）。

---

## 阶段行为

### Discovery 轨

**允许**

- 调研、对比表、风险列表、非功能底线整理。
- ADR **草案** 与 spike **计划**；为验证假设而写的 **少量、可丢弃** 代码（须标注 disposable）。

**禁止（默认）**

- 在未过 **G1** 前，批量创建「正式」模块树、完整 CMake 工程、或与 ADR 未记录架构不一致的目录。
- 将 Tenet 文档中的 **示例路径** 当作必须采用的 repo 形状。

**例外**

- 用户 **明确** 要求 spike，且说明 **可丢弃** → 仅限 spike 范围，并在结论中回收或删除。

### G0 未过（用户项目）

- 不得替用户 **选定** 最终架构、第三方栈、发布渠道。
- 应引导完成 [`process/gates/G0-charter.md`](process/gates/G0-charter.md) 中的问项。

### G1 未过

- 不得合并 **互相冲突** 的架构叙述；不得以「先搭架子再说」为由跳过 [`process/discovery/exit-criteria.md`](process/discovery/exit-criteria.md)。
- 可继续 Discovery；出口满足后再走 G1 评审。

### Delivery 轨（G1 通过后）

- 目录、模块、CMake 等 **须与已批准基线记录 / ADR 一致**；变更走 ADR 或 v2 变更关口（G2）。
- 迭代内交付 **可演示增量**；发布与质量门禁遵循 OVERVIEW 中的 **语义**（非 Tenet 绑定的 CI 模板）。

---

## 架构与选型

- 架构答案 **必须来自对话结论**，并 **落盘为 ADR 或基线记录**（路径由用户项目自定；Tenet 建议 `docs/adr/`）。
- Tenet 只提供 **权衡维度与教练问法**（v2 `discovery/facilitation.md`），**不给**「默认三层 / 默认 monorepo」答案。
- 引用第三方、许可证、合规：须在 Discovery 出口前扫过红线（见 exit-criteria）。

---

## 文档地图（v1）

| 文档 | 用途 |
|------|------|
| [`process/OVERVIEW.md`](process/OVERVIEW.md) | 总流程、嵌入方式、v2 路线图 |
| [`process/gates/G0-charter.md`](process/gates/G0-charter.md) | 立项关口 |
| [`process/gates/G1-baseline.md`](process/gates/G1-baseline.md) | Discovery → Delivery；正式落盘许可 |
| [`process/discovery/exit-criteria.md`](process/discovery/exit-criteria.md) | Discovery 硬出口 |

v2 计划（未写不入链）：`definition-of-done.md`、`choose-scrum-kanban.md`、`collaboration/*`、`cpp/*`、`adoption/*`。

---

## 多工具一致

在 Cursor、Claude Code、Copilot、VS Code 等场景中，应 **优先 @ 本文件** 或 @ `process/OVERVIEW.md`，避免各工具各写一套流程。  
**不要** 在对话中发明与上述文档矛盾的「第二套 Tenet 流程」。

---

## 附录：流程专有名词

| 中文 | English |
|------|---------|
| 关口 | Stage-Gate |
| 立项 | Charter / G0 |
| 基线 | Baseline / G1 |
| 探索轨 | Discovery track |
| 交付轨 | Delivery track |
| 完成定义 | Definition of Done (DoD) |
| 架构决策记录 | Architecture Decision Record (ADR) |
| 单一事实来源 | Single Source of Truth (SSOT) |
| 产品增量 | Product Increment |
| 待办列表 | Backlog |
| 看板 | Kanban |
| 迭代 | Sprint |
| 质量门禁 | Quality gate |
| 技术探针 | Spike |
| 可丢弃代码 | Disposable code |

---

文档 v1.0 · 与 [`process/OVERVIEW.md`](process/OVERVIEW.md) 版本一致。
