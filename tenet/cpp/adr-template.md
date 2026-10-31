# ADR 模板（Architecture Decision Record）

复制到 **用户项目** `docs/adr/NNNN-简短标题.md`（`NNNN` 四位递增）。  
Tenet **不** 规定目录必须叫 `docs/adr/`，但 **须** 有等价决策记录。

**状态**：草案 → 已接受 / 已废弃 / 已 supersede（被新 ADR 取代时链到新编号）

---

```markdown
# ADR-NNNN：标题（动词 + 决策对象）

- **状态**：草案 | 已接受 | 已废弃 | superseded by ADR-MMMM
- **日期**：YYYY-MM-DD
- **决策者**：（角色，非必须实名）

## 背景

要解决什么问题？与 G0 charter / baseline 哪条相关？

## 决策

我们 **选择** ……（一句话结论）

## 备选方案

| 方案 | 优点 | 缺点 |
|------|------|------|
| A | | |
| B | | |

（若否决策：为什么不做某类方案）

## 后果

- **正面**：
- **负面 / 代价**：
- **对构建/目录/依赖的影响**：（Tenet 不预设形状，写你项目的事实）

## 合规与许可证

是否触及 G0 红线？第三方/license 影响？

## 关联

- G0 / baseline 版本：
- 若 supersede：旧 ADR 链接：
- Discovery / spike 链接（若有）：
```

---

## 使用时机

| 时机 | 说明 |
|------|------|
| **Discovery** | 关键选型对比后，状态 **已接受** 再进 G1 |
| **Delivery** | 结构性变更 → 先 ADR **已接受**，再改代码；见 [`../process/gates/G2-change.md`](../process/gates/G2-change.md) |
| **工具链对齐** | 如 IDE/编译器/CMake 生成器（试点 ADR-0002 类） |

---

## AI 行为

- **禁止** 在 ADR 仍为 **草案** 时，按该决策批量改正式工程树（spike 除外）。  
- 协助填模板时 **逐节提问**；不得替用户写「已接受」除非用户确认。

---

## 相关文档

- [`../process/discovery/exit-criteria.md`](../process/discovery/exit-criteria.md)
- [`../process/gates/G2-change.md`](../process/gates/G2-change.md)
- [`../AGENTS.md`](../AGENTS.md)

---

文档 v1.3 · Tenet cpp（元层模板，非工程脚手架）
