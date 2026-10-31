# G2 变更关口（Change / Stage-Gate 2）

G2 用于 **Baseline 已通过（G1）之后** 的 **重大变更**：  
不能当作普通 Delivery 小项直接做，须 **先决策、再升版基线、再落代码**。

**Tenet 仍不预设** repo 形状；G2 管的是 **变更是否合法、是否已记录**。

---

## 何时必须走 G2

出现 **任一条** 即 **必须 G2**（不能只写 backlog 或 silent merge）：

| # | 触发条件 |
|---|----------|
| 1 | 改变 **模块边界** 或「单仓/多仓/库拆分」策略 |
| 2 | 更换 **主构建系统** 或 **主工具链**（compiler、generator、major CMake 策略） |
| 3 | 引入 **新的主要第三方** C++ 依赖或改变分发/license  posture |
| 4 | 扩大 **G0 charter 非目标之外** 的 scope |
| 5 | 改变 **对外 API / 集成契约**（行为或兼容承诺） |
| 6 | **Baseline 版本** 需从 vN 升到 vN+1 的结构性调整 |

**不必 G2**（走 Delivery + DoD 即可）：

- 在 baseline 已允许的形态内：改 `main`、加测试、修 bug、改文案  
- 与已接受 ADR **一致** 的实现细节  
- 工具链 **补丁级** 升级且 ADR/ baseline 已声明兼容范围  

不确定时 → 走 G2 或先写 **ADR 草案** 讨论。

---

## 前置条件

- 项目 **G1 已通过**，存在 `docs/baseline.md`（或等价）  
- 变更提议已 **书面化**（Issue、PR 描述或 `docs/changes/G2-xxx.md`）

---

## G2 流程（最小）

```text
提议 → ADR（对比+结论）→ baseline 升版 → G2 评审 → Delivery 实现
```

| 步骤 | 产出 |
|------|------|
| 1. 提议 | 变更动机、影响面、是否触 charter 非目标 |
| 2. ADR | 新 ADR 或修订；状态 **已接受**（模板 [`../../cpp/adr-template.md`](../../cpp/adr-template.md)） |
| 3. Baseline 升版 | `baseline.md` 版本 vN→vN+1 或 **变更记录附录** + 日期 |
| 4. G2 评审 | 角色同 G1 或更轻；结论写入 baseline 或 `docs/gates/G2.md` |
| 5. Delivery | 按 DoD 实现；用 [`../prompts/delivery-item.md`](../prompts/delivery-item.md) |

---

## G2 记录模板（用户项目，建议）

`docs/gates/G2.md` 或单次 `docs/gates/G2-YYYY-MM-DD-标题.md`：

```markdown
# G2 变更记录

- **关联 ADR**：
- **Baseline**：v___ → v___
- **触发项**（上表 1–6 编号）：
- **摘要**：
- **G0 非目标检查**：通过 / 需先修订 charter
- **结论**：通过 / 不通过 / 搁置
- **日期**：
- **签字（角色）**：
```

---

## 通过标准

**G2 通过** 当且仅当：

1. 相关 ADR **已接受**，且与 G0 **无未解决冲突**  
2. **Baseline 已升版** 或变更附录已写入  
3. G2 记录 **结论：通过**  
4. 若触 charter 非目标 → **须先 G0 修订**，再 G2  

---

## 未通过 / 搁置

- **不得** 按新架构批量 merge 正式树  
- 可保留 **disposable spike**；结论后删除或 ADR 化  

---

## AI 行为

- 识别到上表 **必须 G2** 的触发项 → **停止** 直接改 CMake/模块结构；引导 ADR + G2 模板。  
- G2 未通过 → 仅允许 **不扩大结构** 的 Delivery。  
- G2 通过后 → 与 **新 baseline** 一致地改代码。  
- 完成后发 [`../prompts/stage-feedback.md`](../prompts/stage-feedback.md) 中合适停步块（可自拟「G2 通过后」四问，结构同 G1 停步）。

---

## 与 G0 / G1 的关系

| 关口 | 关系 |
|------|------|
| **G0** | scope / 非目标被突破 → 先修 charter |
| **G1** | 首次批准 baseline；G2 是 **后续** 重大变更 |
| **Discovery** | 全新方向可能回到 Discovery + exit，再 **新 G1**（极少）；多数情况 G2 + ADR 即可 |

---

## 相关文档

- [`G1-baseline.md`](G1-baseline.md)
- [`../../cpp/adr-template.md`](../../cpp/adr-template.md)
- [`../prompts/g2-request.md`](../prompts/g2-request.md)
- [`../delivery/definition-of-done.md`](../delivery/definition-of-done.md)
- [`../discovery/facilitation.md`](../discovery/facilitation.md) — ABCD「是否扩 scope / 换工具链」
- [`../../AGENTS.md`](../../AGENTS.md)

---

文档 v1.3 · Tenet process
