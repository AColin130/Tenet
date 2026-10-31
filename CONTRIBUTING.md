# 贡献 Tenet（Contributing）

感谢改进 **Tenet 元层文档**（`tenet/**`）。本仓 **不含业务 C++**；PR 应聚焦流程、AI 引导与协作说明。

完整流程 SSOT 见 [`tenet/AGENTS.md`](tenet/AGENTS.md)。**本文件 SSOT** 为：**Git 提交与 PR 写法（Tenet 官方仓）**。

---

## 改哪里

| 可以改 | 不要改 |
|--------|--------|
| `tenet/**` 流程与协作文档 | 在根 [`AGENTS.md`](AGENTS.md) **堆流程正文**（根文件仅路由） |
| 根 `README.md`、`LICENSE`、**本文件**、`CHANGELOG.md` | 在本仓添加「示例 C++ 工程树」当产品交付 |

变更后保持与 [`tenet/process/OVERVIEW.md`](tenet/process/OVERVIEW.md) **互链一致**。

---

## Commit 消息（Tenet 官方仓约定）

### 语言

- **单次 commit 全文用一种语言**：你撰写时用 **中文** → commit 用 **中文**；用 **英文** → commit 用 **英文**。
- **不要在同一条 commit 里** subject 中文、body 英文乱混（除非 body 仅引用文件路径/链接）。
- **历史已存在另一种语言** 的 commit 无需改写；**从新 commit 起** 遵守上条。

### 格式

- **第一行 subject 必填**，建议 **Conventional Commits 前缀**（前缀用英文便于工具识别）：
  - `docs:` — 文档（Tenet 最常见）
  - `fix:` — 纠正错误链接/条文
  - `chore:` — 元数据、版本说明、无实质流程变更
- **示例（中文 subject）**：`docs: 补充 CONTRIBUTING 与 commit 语言约定`
- **示例（英文 subject）**：`docs: add CONTRIBUTING commit language policy`

### 何时建议 subject 用英文

仅当本次变更 **主要面向国际读者** 时（例如 README 顶部 English block、LICENSE 旁对外说明）：**建议** subject 用 **英文**，body 可用中文写维护者说明。

### Body（可选）

- 写 **为什么**（解决什么误解/协作问题），不必罗列所有文件名。
- PR 描述与 commit 语言 **可一致**（同一 PR 内不必中英各写一遍）。

---

## Pull Request

1. 说明 **解决了什么问题**（用户/AI/维护者哪类痛点）。
2. 若改关口或 AI 强制行为，指出 **对应文档**（如 `tenet/AGENTS.md`、`process/gates/*`）。
3. 不要求长文；**一条 commit 一种语言** 同样适用于 PR 标题（与主要 commit 一致即可）。

---

## AI 协助本仓时的约定

在 **Tenet 官方仓** 内让 AI 生成 commit message 时：

- 与用户当次说明 **同语言**；
- subject 带 `docs:` / `fix:` / `chore:`；
- **不** 在根 `AGENTS.md` 写流程；**不** 发明与 `tenet/AGENTS.md` 矛盾的流程。

（业务 C++ 仓的 Git 约定由 **该仓** 自定；可选模板见 [`tenet/collaboration/commit-conventions.md`](tenet/collaboration/commit-conventions.md)。）

---

## 获取帮助

- [GitHub Issues / Discussions](https://github.com/AColin130/Tenet)

---

与 [`tenet/process/OVERVIEW.md`](tenet/process/OVERVIEW.md) 文档版本同步维护。
