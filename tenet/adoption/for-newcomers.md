# 新手跟 Tenet（AI 协作）

面向 **主要靠 AI 写 C++、第一次走关口** 的读者。不要求先懂 CMake；要求愿意 **按顺序** 做，并 **复制模板** 跟 AI 说话。

---

## 30 秒：你要记住的三句

1. **Tenet 不给你现成工程树** — 它规定 **什么时候才能大批量建目录**。  
2. **权威在 `tenet/AGENTS.md`** — 对话里 @ 它；根目录 `AGENTS.md` 若是「胶水」，也要指向 tenet。  
3. **做完一步会停** — AI 会问你还缺什么；你 **回复后再继续**（见 [`../process/prompts/stage-feedback.md`](../process/prompts/stage-feedback.md)）。

---

## 第一次打开仓库读什么

| 顺序 | 文件 | 目的 |
|------|------|------|
| 1 | 业务仓根 `AGENTS.md`（若有） | 本地怎么构建、tenet 在哪 |
| 2 | [`../AGENTS.md`](../AGENTS.md) | AI 规则 |
| 3 | [`../process/OVERVIEW.md`](../process/OVERVIEW.md) | 总流程图 |
| 4 | 需要动手时 | [`../process/prompts/g0-start.md`](../process/prompts/g0-start.md) **整段复制** 给 AI |

**先别读** 全部 gates 正文；用 **模板 + AI 逐节问** 即可。

---

## 阶段白话

| 阶段 | 人话 | 你能看到什么 |
|------|------|----------------|
| **G0** | 这项目做啥、不做啥 | `docs/charter.md` |
| **Discovery** | 架构怎么选、写 ADR、小 spike | `docs/adr/`、`docs/discovery/` |
| **G1** | 允许 **正式** 写 CMake/模块 | `docs/baseline.md` |
| **Delivery** | 一项一项做，做完停一步 | 代码 + DoD |

**没过 G1** = 不要让 AI 「先把整个项目目录生成好」。

---

## 复制即用（最常用三个）

1. **开工** → [`../process/prompts/g0-start.md`](../process/prompts/g0-start.md)  
2. **做一项功能** → [`../process/prompts/delivery-item.md`](../process/prompts/delivery-item.md)（仅 **G1 后**）  
3. **AI 说太长不知道干啥** → 让它读 [`../collaboration/ai-collaboration.md`](../collaboration/ai-collaboration.md)，并 **贴一个模板**

---

## 名词怕不懂

看 [`../AGENTS.md`](../AGENTS.md) 文末 **附录**（关口、Discovery、DoD、ADR…）。  
第一次见 **ADR** 可以想成：**我们为什么选 A 不选 B 的一页纸**。

---

## 试点已经 hello world 了，我下一步？

- 新想法 **不改范围** → 写进 backlog，用 **delivery-item** 模板一项一项做。  
- 要 **换工具链 / 扩 scope** → 跟 AI 说，走 **ADR + G2**（[`G2-change.md`](../process/gates/G2-change.md)、[`adr-template.md`](../cpp/adr-template.md)）。  
- 不用 **补很多正式需求文档**；Tenet 要的是 **该落盘时落盘**（charter / ADR / baseline）。

---

## 推荐：拷贝 `tenet/` + 一个业务仓长期用

Tenet **官方仓不含你的业务代码**；C++ 只在 **你自己的仓库** 里写。验证 Tenet 是否好用，用 **单独试点仓** 即可，**不必** 每测一次 Tenet 就新开项目。

| 做法 | 说明 |
|------|------|
| **拷贝 `tenet/`** | 从 Tenet 官方仓复制 `tenet/` 目录（建议同时保留 [LICENSE](../../LICENSE) 文本） |
| **单仓** | charter、ADR、baseline、源码 **同一仓库** 长期维护 |
| **何时再拷** | 只有想要 **新手册**（新模板、DoD、G2 等）时再覆盖/合并 `tenet/` |
| **不要** | 用 Tenet 官方仓 **根** `AGENTS.md` 覆盖业务仓根；业务根用 **胶水**（见 [`../process/OVERVIEW.md`](../process/OVERVIEW.md) 嵌入一节） |

**Submodule** 可选；不熟 git 时 **拷贝就够**。

---

## 和「更新 Tenet 文档包」的关系（可选）

若业务仓里的 `tenet/` 是 **拷贝** 的：想要新文档时再拷一次官方 `tenet/`（若你改过 tenet 内文件，注意合并）。

若用 **submodule**：官方更新后在业务仓 `git submodule update --remote tenet`（路径按实际）。

**不更新 tenet/** 也可以继续 **构建和业务 Delivery**；只是没有最新 **复制模板 / 流程条文**。

---

## 相关文档

- [`../process/gates/G0-charter.md`](../process/gates/G0-charter.md)
- [`../process/gates/G2-change.md`](../process/gates/G2-change.md)
- [`../cpp/adr-template.md`](../cpp/adr-template.md)
- [`../process/delivery/definition-of-done.md`](../process/delivery/definition-of-done.md)
- [`for-leads.md`](for-leads.md)
- 仓库 [`README.md`](../../README.md)

---

文档 v1.4 · Tenet adoption
