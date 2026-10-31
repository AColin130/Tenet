# Git 提交约定（Commit Conventions）

**模板**：业务仓 **可选** 从 Tenet 拷贝或改写本节，写入 **`CONTRIBUTING.md`** 或 **`docs/engineering.md`**。  
**Tenet 官方仓** 的权威条文见仓库根 **[`CONTRIBUTING.md`](../../CONTRIBUTING.md)**（语言、前缀、PR）。

Tenet **不强制** 所有 C++ 业务仓采用与本官方仓相同的语言策略；在 **G1 baseline** 或 G0 中 **写一句** 即可。

---

## 推荐规则（可复制到用户项目）

### 1. 单 commit 单语

- 本次撰写用中文 → commit **全文中文**（含 subject/body）。
- 本次撰写用英文 → commit **全文英文**。
- 避免一条 commit 内中英 subject/body 混排。

### 2. Subject 格式

```
<type>: <简短说明>
```

常用 `type`：`feat` `fix` `docs` `refactor` `test` `chore`（前缀英文便于工具；说明可用团队常用语言）。

### 3. 与 Tenet 关口的关系

| 变更类型 | Git 之外还要什么 |
|----------|------------------|
| 普通 Delivery | DoD + Review（见 [`code-review.md`](code-review.md)） |
| 结构性 / 工具链 | **G2 + ADR** 先于或随同 merge |
| 仅 docs/charter/adr | 仍建议清晰 commit，便于 bisect |

Git 约定 **不能替代** G0/G1/G2/ADR。

### 4. 国际化团队（可选）

若仓库 **对外** 且 commit 历史需给不读中文的人看：团队可 **另定**「commit 统一英文、PR 中文讨论」——在 baseline **显式写** 覆盖本节。

---

## 相关文档

- Tenet 官方仓 [`CONTRIBUTING.md`](../../CONTRIBUTING.md)
- [`for-leads.md`](../adoption/for-leads.md)
- [`../process/delivery/definition-of-done.md`](../process/delivery/definition-of-done.md)

---

文档 v1.4 · Tenet collaboration（模板，非强制链）
