# Tenet

**Tenet** is an open meta-layer for **C++ team rules + AI guidance** — not a scaffold with a fixed architecture.  
It provides Stage-Gates, Discovery/Delivery tracks, and AI constraints so **you and your AI** choose structure in conversation, then materialize CMake/modules in **your** repo.  
**Authority:** [`tenet/AGENTS.md`](tenet/AGENTS.md) (root [`AGENTS.md`](AGENTS.md) is routing only).  
**Start:** [`tenet/process/OVERVIEW.md`](tenet/process/OVERVIEW.md).  
**License:** [MIT](LICENSE) — use, copy, modify, and redistribute freely (keep copyright notice).

---

# Tenet（中文）

**Tenet** 是面向 C++ 团队的开源 **「规矩 + AI 引导」** 包。  
它 **不是** 克隆即用、带固定目录/ monorepo / exe 模板的脚手架；它提供 **怎么选、怎么谈、怎么落盘、怎么协作** 的流程与 AI 边界，让 **你 + AI** 在用户自己的项目里长出工程形状。

**隐喻**：Tenet = **教练 + 裁判手册**；你的项目 = 场上怎么踢，由引导问出来。

---

## 适合谁

- 需要 **20+ 人规模协作习惯**（关口、双轨、Review 语义）的 C++ 团队  
- 希望在 Cursor、Claude Code、Copilot、VS Code 等工具下 **同一套 SSOT**，减少「AI 各写各的、工程一团乱」  
- **编程新手** 在 AI 协助下跟流程（v2 将补 `adoption/` 裁剪说明）

---

## Tenet 不是什么

- 不提供默认 **三层工程树 / monorepo 成品**  
- 不捆绑必选 **CI YAML 模板** 作为架构一部分  
- 不在 Tenet 仓库里替你的业务 **做决定** — 决定落在你的 ADR 与基线里

---

## 快速开始

### 仅阅读或贡献 Tenet

1. 打开 **[`tenet/AGENTS.md`](tenet/AGENTS.md)**（流程与 AI 权威）  
2. 阅读 **[`tenet/process/OVERVIEW.md`](tenet/process/OVERVIEW.md)**（权威链、双轨、关口总图）  
3. 按阶段阅读：
   - 立项 → [`tenet/process/gates/G0-charter.md`](tenet/process/gates/G0-charter.md)
   - Discovery 出口 → [`tenet/process/discovery/exit-criteria.md`](tenet/process/discovery/exit-criteria.md)
   - 基线 → [`tenet/process/gates/G1-baseline.md`](tenet/process/gates/G1-baseline.md)

若 IDE 先打开根目录 [`AGENTS.md`](AGENTS.md)，其中指令会指向 **`tenet/AGENTS.md`** — 根文件 **不含** 流程正文。

### 嵌入已有 C++ 业务仓

1. 将 **`tenet/`** 目录引入业务仓（submodule、subtree 或拷贝），并保留 **[`LICENSE`](LICENSE)**（与 `tenet/` 同级或置于 `tenet/LICENSE` 均可）  
2. 在 **业务仓根** 编写胶水 `AGENTS.md`（模板见 [`tenet/process/OVERVIEW.md`](tenet/process/OVERVIEW.md)「将 tenet/ 嵌入已有 C++ 仓」一节）  
3. 在 **用户项目** 走 G0 → Discovery → G1，再 Delivery — **不要** 跳过关口批量生成工程树  

流程权威始终是 **`./tenet/AGENTS.md`**，不是 Tenet 官方仓的根路由文件。

---

## 流程一览（均衡默认）

| 层 | 内容 |
|----|------|
| 外层 | 轻 **Stage-Gate**：G0 立项、G1 基线 |
| 双轨 | **Discovery**（探索）→ **Delivery**（交付） |
| 内层 | **Scrum** 或 **Kanban**（G1 基线中择一记录） |
| 发布 | **质量门禁语义** + 能自动化就多自动化 |

细节见 [`tenet/process/OVERVIEW.md`](tenet/process/OVERVIEW.md)。

---

## 仓库结构（v1）

```text
AGENTS.md                 # 路由 stub → tenet/AGENTS.md
LICENSE                   # MIT
README.md                 # 本文件（顶英下中）
tenet/
  AGENTS.md               # 流程与 AI SSOT
  process/
    OVERVIEW.md
    gates/G0-charter.md
    gates/G1-baseline.md
    discovery/exit-criteria.md
```

---

## 文档版本

- **v1.0**：五件套 + README + MIT LICENSE（Delivery 迭代 4）  
- **v2 规划**：DoD、Scrum/Kanban 细则、C++ 协作规范、`adoption/` 等 — 见 OVERVIEW「v2 路线图」

---

## 贡献

欢迎 Issue / PR 改进 **Tenet 元层文档**（`tenet/**`）。  
修改流程正文时 **勿** 在根 `AGENTS.md` 堆规则；维护约定见根 `AGENTS.md`「给人」一节。

---

## 许可证

本仓库采用 **[MIT License](LICENSE)**。

- **为什么用 MIT**：常见、短、**谁都能用** — 可商用、可改、可再分发，只需保留版权声明。  
- **和 Apache-2.0 比**：MIT 更简单；若你未来特别在意「专利授权」条款，可再考虑换 Apache-2.0（v1 选 MIT 即可满足「随便用」）。  
- **嵌入业务仓**：随 `tenet/` 一并保留 LICENSE 文本即可；Tenet 文档 **不** 自动覆盖你业务代码的许可证。

---

## 权威链（一句话）

**根 `AGENTS.md` 路由 → `tenet/AGENTS.md` 规范 → `tenet/process/*` 细节。**
