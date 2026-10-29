# G1 基线关口（Baseline / Stage-Gate 1）

G1 是 **Discovery → Delivery** 的交接关口：  
在 **G0 已通过** 且 **Discovery 出口已满足** 的前提下，评审并 **批准正式工程基线** —— 此后才允许在用户项目中 **系统性落盘** 目录、模块、构建描述等与基线一致的实现。

G1 **不是** 第一次写代码（spike 可在 Discovery）；G1 **是** 第一次 **承诺「这就是我们要建的东西」** 并进入迭代交付节奏。

---

## 关口目的

| 批准的内容 | 不批准的内容 |
|------------|----------------|
| 与 ADR 一致的架构原则与模块边界 | 未 closed 的 spike 目录默认并入 |
| 集成策略与主要依赖 | 详细到函数级的实现 |
| 交付节奏选择（Scrum **或** Kanban） | Tenet 预设的 repo 模板形状 |
| 质量/合并/发布的 **门禁语义**（见 OVERVIEW） | 具体 CI 文件名与流水线 YAML |

Tenet **不规定** CMake 必须几层；基线记录的是 **决策与边界**，不是 **万能目录树**。

---

## 前置条件

进入 G1 评审前，必须同时满足：

1. [`G0-charter.md`](G0-charter.md) — 用户项目 **G0 状态：通过**
2. [`../discovery/exit-criteria.md`](../discovery/exit-criteria.md) — 出口清单 **全部满足**，且有 `EXIT.md` 或等价 **人工确认**

任一不满足 → **退回 Discovery**，不得 G1 通过。

---

## 基线应包含什么

建议在 **用户项目** 维护 `docs/baseline.md`（或 `docs/gates/G1.md`），G1 通过后版本化为 **Baseline v1**（后续重大变更升 v2 或走 v2 G2）。

### 建议结构

```markdown
# 工程基线 Baseline v1

## 1. 引用
- G0 charter 链接：
- Discovery EXIT 链接：
- ADR 索引链接：

## 2. 架构原则（与 ADR 一致）
- 模块/边界简述：
- 禁止事项（如禁止循环依赖、禁止某层直接调某层）：

## 3. 构建与仓库形态（用户决策，非 Tenet 模板）
- 单仓/多仓：
- 构建系统（如 CMake）及最低工具链版本：
- 第三方获取方式（包管理/conan/vcpkg/源码）：

## 4. 集成与接口
- 对外接口清单或指针：
- 与环境/配置相关的约定：

## 5. 交付方式（二选一，须写明）
- [ ] Scrum：迭代长度 ___ 周；Review 演示约定：
- [ ] Kanban：WIP 限制 ___；列定义指针：

## 6. 质量门禁（语义）
- 合并前必须：
- 发布候选必须：

## 7. G1 结论
- 状态：通过 / 不通过
- Baseline 版本：v1
- 日期：
- 签字（角色）：
```

AI 协助撰写时 **必须** 与已有 ADR 交叉引用；**禁止** 在基线中发明 ADR 未覆盖的架构。

---

## 基线不应包含什么

- 未在 Discovery 中 **决策** 的「临时方便」结构
- 与 G0 **非目标** 冲突的 scope
- 复制 Tenet 文档里的 **示例胶水** 当作本项目架构
- 未标注 disposable 的 spike 残留

---

## 通过标准

**G1 通过** 当且仅当：

1. 前置条件（G0 + exit-criteria）已满足  
2. `baseline.md`（或等价）**第 1–6 节完整**，且与 ADR **无冲突**  
3. 评审参与者（至少技术负责人 + 产品或业务代表 **角色**，小团队可一人兼）确认 **可在此基线上开始 Delivery**  
4. 第 7 节 **状态：通过**，Baseline 版本号已赋  

**Tenet 维护者** 对 Tenet 文档包的 G1：指 v1 五件套互链完整、可独立指导用户项目 —— 与 OVERVIEW 中 v1 范围一致。

---

## 未通过 G1 时

| 情况 | 动作 |
|------|------|
| 缺口在调研/选型 | 回 Discovery，补 ADR 或 exit 项 |
| 缺口在 charter | 回 G0 修订范围或红线 |
| 基线过大/过糊 | 缩小 Baseline v1 范围，明确 Phase 2 为 Delivery backlog |

AI：**不得** 因 G1 未通过而继续批量添加「正式」工程文件；可继续 disposable spike。

---

## 通过后：Delivery 默认行为

1. **落盘** 与 Baseline v1 **一致** 的目录与构建文件；新结构 **先 ADR 再改**（v1 重大变更见下节）  
2. **Scrum**：按基线中的迭代长度计划；每迭代 Review **可演示增量**  
3. **Kanban**：按 WIP 与列定义流动；不强行虚构 Sprint  
4. **合并与发布**：满足基线第 6 节门禁语义；自动化能覆盖则覆盖  

DoD 细项见 [`../delivery/definition-of-done.md`](../delivery/definition-of-done.md)；v1 重大变更见下节。

---

## 重大变更（v1 无独立 G2 文档）

Baseline v1 通过后，若出现以下情况，**须停止当作小改动直接做**：

- 改变模块边界或主依赖栈  
- 扩大 G0 非目标之外的 scope  
- 改变集成契约或对外 API 承诺  

**v1 要求**：

1. 新 ADR 或修订 ADR，状态 **已接受**  
2. 更新 `baseline.md` 升版（v2…）或附录 **变更记录**  
3. **人工评审**（与 G1 相同或更轻的角色组合），在基线文档中记录 **变更通过日期**  

**v2** 将提供 [`G2-change.md`](G2-change.md) 独立关口；v1 不强制文件名，但 **不得** 跳过 ADR + 基线升版。

---

## AI 行为（G1 前后对照）

| 阶段 | AI |
|------|-----|
| **G1 前** | 见 [`../../AGENTS.md`](../../AGENTS.md) Discovery 禁止项 |
| **G1 通过后** | 可按 Baseline v1 创建/修改工程树；每项结构性变更须 **可追溯 ADR** |
| **任何时候** | 不引入 Tenet 未授权的第二套流程；不默认 monorepo 三层模板 |

---

## 产出物

| 对象 | 建议路径（用户项目） |
|------|----------------------|
| 基线记录 | `docs/baseline.md` 或 `docs/gates/G1.md` |
| ADR | `docs/adr/` |
| Discovery 出口 | `docs/discovery/EXIT.md` |

Tenet 仓库 **不包含** 用户 baseline 实例。

---

## 本阶段结束（教练）

G1 标记 **通过** 后，AI **必须停步** 并发出 [`../prompts/stage-feedback.md`](../prompts/stage-feedback.md)「G1 通过后」反馈块；申请 G1 可用 [`../prompts/g1-request.md`](../prompts/g1-request.md)。见 [`../discovery/facilitation.md`](../discovery/facilitation.md)。

---

## 相关文档

- [`G0-charter.md`](G0-charter.md)
- [`../discovery/exit-criteria.md`](../discovery/exit-criteria.md)
- [`../discovery/facilitation.md`](../discovery/facilitation.md)
- [`../OVERVIEW.md`](../OVERVIEW.md)
- [`../../AGENTS.md`](../../AGENTS.md)

---

文档 v1.1 · Tenet process（与 OVERVIEW 版本一致）
