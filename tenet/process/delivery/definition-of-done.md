# 完成定义（Definition of Done）

DoD 回答：**什么叫「这一项 Delivery 做完了」**。  
G1 通过后，每个 backlog / 看板项在 **标记完成前** 须满足 **本项目 baseline 第 6 节（质量门禁语义）** 与 **本 DoD**。

Tenet **不** 规定具体测试框架或 CI 文件名；下列为 **C++ 项目通用最小集**，可在 G1 基线中 **增删** 并写进 `docs/baseline.md`。

---

## 单项 Delivery 完成（默认）

在 **G1 已通过** 且变更 **不扩大 G0 非目标** 的前提下，一项工作 **完成** 当：

| # | 条件 |
|---|------|
| 1 | 与 **Baseline** 及 **相关 ADR** 一致；结构性变更已有 **已接受 ADR** |
| 2 | **验收方式** 在开工前已写明（如：命令、exit 0、指定测试名），且 **本机或 CI 已通过** |
| 3 | **构建** 按项目 G0/baseline 约定成功（Debug 或 baseline 指定配置） |
| 4 | **Review**：见 [`../../collaboration/code-review.md`](../../collaboration/code-review.md)；单人可自检 + Delivery 停步 |
| 5 | **无** 未标注 disposable 的 spike 残留进正式树 |
| 6 | 文档：若改对外行为/API，**用户可见说明** 或 ADR 已更新 |
| 7 | **Tenet 停步**：AI 或负责人已发 [`../prompts/stage-feedback.md`](../prompts/stage-feedback.md)「Delivery 单项停步」，用户确认后再开下一项 |

**hello-world 级试点**：often 仅须 2 + 3 + 7（命令跑通、exit 0、停步确认）。

---

## 合并到主分支（语义 · 合并前门禁）

与 [`../OVERVIEW.md`](../OVERVIEW.md)「自动化与发布」一致，**默认**：

- 构建通过  
- baseline 要求的 **关键测试** 通过  
- 无已知 **阻断** 编译警告策略（若 baseline 有写）  
- 许可证/第三方 **未违反 G0 红线**  

---

## 发布候选（可选 · baseline 启用时）

仅当 G0/baseline 声明 **有发布节奏** 时适用：

- 可复现构建产物  
- 版本号 / 变更说明策略已遵循  
- 回滚或降级路径 **已知**  

---

## 与 Scrum / Kanban 的关系

| 方式 | DoD 何时检查 |
|------|----------------|
| **Scrum** | 每个 Product Backlog 项在 Sprint 内完成时；Sprint Review 演示 **满足 DoD** 的增量 |
| **Kanban** | 卡片进入「完成」列前 |

选用哪种方式见 [`choose-scrum-kanban.md`](choose-scrum-kanban.md)；在 G1 baseline 中 **写死一种**。

---

## AI 行为

- 声称「做完了」前，对照 **本 DoD + baseline 第 6 节** 逐条说明。  
- 缺验收命令或 exit 标准 → **先问清**，再改代码。  
- 完成后 **必须** Delivery 停步反馈，**不** 自动开下一项。

---

## 相关文档

- [`../gates/G1-baseline.md`](../gates/G1-baseline.md)
- [`choose-scrum-kanban.md`](choose-scrum-kanban.md)
- [`../prompts/delivery-item.md`](../prompts/delivery-item.md)
- [`../../AGENTS.md`](../../AGENTS.md)

---

文档 v1.2 · Tenet delivery
