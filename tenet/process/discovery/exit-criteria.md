# Discovery 出口标准（Exit Criteria）

Discovery 轨的目标：**在写「正式工程基线」之前**，把该谈的谈完，把该证的证完，减少返工与 AI 各写各的架构。

本文档是 **硬出口清单**。未 **全满足** 前：

- **不得** 召开 G1 基线评审（或不得将 G1 标为通过）；
- **AI 不得** 批量创建与结论不一致的模块树、CMake 工程或「默认模板式」repo 结构。

满足出口 → 仍须过 [`../gates/G1-baseline.md`](../gates/G1-baseline.md)，G1 通过后才进入 **Delivery** 正式落盘。

---

## 本文件地位

| 关系 | 说明 |
|------|------|
| **输入** | 已通过 [`../gates/G0-charter.md`](../gates/G0-charter.md) 的项目 charter |
| **输出** | G1 评审材料 + 基线记录草案 |
| **SSOT** | Discovery 是否「做完」以本清单为准，不以「感觉差不多」为准 |

---

## 出口清单（建议全部满足）

对 **用户 C++ 项目**，下列每一项须有 **可指向的记录**（文档、ADR、表格或仓库内链接）。  
AI 在声称 Discovery 完成前，须 **逐条自检** 并向用户确认。

### 1. 问题与范围陈述稳定

- [ ] 与 G0 charter 一致，无未解释的 scope 膨胀
- [ ] 「不做什么」仍有效且团队/AI 可引用
- [ ] 主要用户或调用方场景已列出（不必完整 PRD）

**记录建议**：`docs/discovery/scope.md` 或 charter 增补节

### 2. 关键选型有对比与结论

- [ ] 影响架构的决策（构建系统、模块边界、主要第三方库等）有 **至少 2 方案对比** 或 **否决策理由**
- [ ] 结论写入 **ADR** 或等价「决策记录」（状态：已接受）

**记录建议**：`docs/adr/0001-*.md` 起

**Tenet 不提供默认答案**；只要求 **过程可审计**。

### 3. 非功能底线已列

- [ ] 性能、可用性、安全、可维护性等中 **本项目在乎** 的项已列出
- [ ] 每条有 **可验证方向**（非「要快」 alone）

**记录建议**：`docs/discovery/nfr.md` 或 ADR 附录

### 4. 集成点与依赖初版

- [ ] 对外 API、消息、文件、数据库等集成点已枚举
- [ ] 上游/下游依赖与 **失败模式** 有初版说明（谁超时、谁降级）

**记录建议**：`docs/discovery/integrations.md` 或依赖矩阵表

### 5. 规模与风险可估

- [ ] 主要工作包可拆分（Epic/里程碑级，精确人天 optional）
- [ ] Top 风险 ≥3 条，每条有 **缓解或 spike 计划**

**记录建议**：`docs/discovery/risks.md`

### 6. 合规 / 第三方 / 许可证已扫

- [ ] 与 G0 红线对照，无未关闭项
- [ ] 计划引入的第三方库许可证与分发方式已 **粗查**

**记录建议**：在 charter 或 `docs/discovery/compliance.md` 引用结论

---

## 仍不能做的事（即使「差不多」）

- 将 **未写入 ADR/基线** 的口头结论当作正式架构落盘
- 以「先搭 CMake 再补 ADR」跳过 ADR（spike 除外，见下节）
- 合并 **互相冲突** 的多版 AI 生成结构而不经决策记录
- 在未 G1 通过时标记「Sprint 1 交付完成」为 **生产基线**

---

## Spike 与可丢弃代码（Disposable）

| 类型 | 规则 |
|------|------|
| **目的** | 验证单一假设（性能、库兼容、构建探测） |
| **范围** | 最小；须标注 `disposable` 或独立目录（如 `spike/`） |
| **生命周期** | 结论写入 ADR 或 discovery 文档后 **删除或归档**；不得 silent merge 进正式树 |
| **AI** | 仅在用户 **明确** spike 请求时编写；结束时提醒回收 |

Spike **不能替代** 上节出口清单中的 **对比与结论**（除非 spike 本身就是对比手段且已记录）。

---

## AI 出口前自检问句

在建议用户进入 G1 前，AI 应能 **基于仓库文档** 回答「是」：

1. G0 文档是否 **状态：通过**？
2. 架构关键决策是否在 **已接受 ADR** 中？
3. 非功能底线是否有 **专门记录** 而非仅聊天？
4. 集成与依赖是否 **有文档** 而非仅代码目录？
5. 是否存在 **未决策** 却已在代码/CMake 中实现的结构？若有，须先 ADR 或回退 disposable。
6. 合规/许可证是否与 G0 红线 **无冲突**？

任一为「否」→ 继续 Discovery，**不** 推进 G1。

---

## 人工确认与标记

Discovery 完成需要 **人** 确认（角色见 G0 charter，通常为技术负责人或等价角色）。

**建议在用户项目** 增加短记录，例如 `docs/discovery/EXIT.md`：

```markdown
# Discovery 出口确认

- exit-criteria 版本：Tenet v1（tenet/process/discovery/exit-criteria.md）
- 自检日期：
- 确认人（角色）：
- 链接：scope / adr / nfr / integrations / risks / compliance
- 结论：满足出口，申请 G1 / 不满足，原因：
```

AI **不得** 代写「确认人」姓名或伪造签字；可协助生成模板与链接清单。

---

## 与 G1 的衔接

- 本清单 **全满足** + `EXIT.md`（或等价）**申请 G1** → 见 [`../gates/G1-baseline.md`](../gates/G1-baseline.md)
- G1 通过 → Delivery；选用 Scrum 或 Kanban 写入 **基线记录**

---

## 与 v2 facilitation 的分工

- **v1（本文）**：**裁判** — 什么条件够格进入 G1
- **v2 `facilitation.md`（规划）**：**教练** — 怎么问、怎么开对比讨论、怎么写 ADR

未写 facilitation 前，AI 仍须遵守 [`../../AGENTS.md`](../../AGENTS.md) 与 G0/G1，用通用提问完成 Discovery。

---

## 相关文档

- [`../gates/G0-charter.md`](../gates/G0-charter.md)
- [`../gates/G1-baseline.md`](../gates/G1-baseline.md)
- [`../OVERVIEW.md`](../OVERVIEW.md)
- [`../../AGENTS.md`](../../AGENTS.md)

---

文档 v1.0 · Tenet process（与 OVERVIEW 版本一致）
