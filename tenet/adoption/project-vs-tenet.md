# 项目文件 vs `tenet/` 包

本文是 **业务仓布局** 的 SSOT：你的需求、代码、关口记录 **放哪**；更新 Tenet 手册 **不会丢什么**；**不会** 误把业务软件 push 到 Tenet 官方仓。

**铁律：`tenet/` 里只有通用规矩；凡「本项目特有」的一律在 `tenet/` 之外。**

---

## 两个仓库，不要混

| | **Tenet 官方仓**（如 `AColin130/Tenet`） | **你的业务 C++ 仓** |
|---|------------------------------------------|---------------------|
| 内容 | 元层文档 `tenet/**`、CONTRIBUTING、README | `src/`、`CMakeLists.txt`、`docs/**`、根胶水 `AGENTS.md` |
| 谁 push | 维护 Tenet 文档的人 | **你 / 你的团队** |
| 业务代码 | **不应出现** | **在这里** |

push **业务仓** = 上传 **你的项目**（常含拷贝进去的 `tenet/` 目录）。  
push **Tenet 官方仓** = 只改框架文档 — **不是** 上传你的软件，除非你误设 remote。

---

## 放哪（用户需求与定稿）

| 内容 | 放哪里（业务仓） | 不要放 |
|------|------------------|--------|
| G0 边界、非目标 | `docs/charter.md` | `tenet/` |
| ADR | `docs/adr/` | `tenet/` |
| Discovery 材料 | `docs/discovery/` | `tenet/` |
| G1 基线 | `docs/baseline.md` | `tenet/` |
| G2 记录 | `docs/gates/` | `tenet/` |
| **待做 / 一半定好的需求** | **`docs/backlog.md`** 或 **本仓 GitHub Issues** | `tenet/` |
| 源码、构建 | `src/`、根 `CMakeLists.txt` 等 | `tenet/` |
| 本地构建命令 | 根 **`AGENTS.md`（胶水）** | Tenet 官方仓根 AGENTS |

### `docs/backlog.md` 最小模板（可复制）

```markdown
# Backlog

> 项目特有需求；更新 `tenet/` 手册 **不会** 覆盖本文件。

## 待做

- [ ] （一句话 + 验收，如：命令 foo exit 0）

## 停车场（暂不排期）

- …
```

Delivery 时用 [`../process/prompts/delivery-item.md`](../process/prompts/delivery-item.md) 逐项做；**改 scope / 工具链** → ADR + [`G2-change.md`](../process/gates/G2-change.md)。

---

## 更新 Tenet 手册会丢吗？

**不会** 丢 charter、backlog、代码 — 只要它们 **不在 `tenet/` 里**。

| 操作 | 会动什么 | 不会动什么 |
|------|----------|------------|
| 用官方新版 **覆盖 `tenet/`** | 仅 `tenet/` 内 md | `docs/**`、`src/**`、根胶水 `AGENTS.md` |
| **Submodule** 更新 `tenet` | 仅 submodule 指针/内容 | 业务仓其余文件 |
| 不更新 `tenet/` | — | 仍可继续编译与 Delivery；只是没有最新模板/条文 |

**更新前建议**：业务仓先 `git commit`；若曾 **改过** `tenet/` 内文件，覆盖前先 diff/合并。

---

## 推荐：拷贝 `tenet/` + 单仓长期维护

1. 业务仓内保留 **`tenet/`**（拷贝或 submodule）+ LICENSE 文本。  
2. 所有项目决策进 **`docs/`** + 源码目录。  
3. 需要新手册时再更新 **`tenet/`**  alone。  
4. 试点验证 Tenet 用 **单独业务仓** 即可，不必每次新开项目。

详见 [`for-newcomers.md`](for-newcomers.md)。

---

## AI 行为（业务仓）

- **禁止** 把项目 backlog、charter 正文、用户定制需求 **写入 `tenet/`**。  
- 对话里定下来的内容 → 引导落盘到 **`docs/`**（或 Issues）。  
- 更新 Tenet 包 → **只** 替换/合并 `tenet/`，**不** 删改 `docs/backlog.md` 等。

---

## 相关文档

- [`for-newcomers.md`](for-newcomers.md)
- [`for-leads.md`](for-leads.md)
- [`../process/OVERVIEW.md`](../process/OVERVIEW.md) — 嵌入 `tenet/`
- [`../AGENTS.md`](../AGENTS.md)

---

文档 v1.4 · Tenet adoption
