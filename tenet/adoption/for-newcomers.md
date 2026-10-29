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
- 要 **换工具链 / 扩 scope** → 跟 AI 说，走 **ADR**（你试点里的 ADR-0002 就是例子）。  
- 不用 **补很多正式需求文档**；Tenet 要的是 **该落盘时落盘**（charter / ADR / baseline）。

---

## 和「更新 Tenet 文档包」的关系（可选）

若业务仓里的 `tenet/` 是 **从 Tenet 官方仓 submodule 拉下来的**：  
官方仓更新后，在业务仓执行 `git submodule update --remote tenet`（路径按你实际）即可拿到新模板。  

若是 **拷贝** 的 `tenet/`，偶尔 **再拷一次** 或改 submodule 即可。  
**试点已 OK** = 不必为 v1.1 专门折腾，除非你想要新模板。

---

## 相关文档

- [`../process/gates/G0-charter.md`](../process/gates/G0-charter.md)
- [`../process/delivery/definition-of-done.md`](../process/delivery/definition-of-done.md)
- 仓库 [`README.md`](../../README.md)

---

文档 v1.2 · Tenet adoption
