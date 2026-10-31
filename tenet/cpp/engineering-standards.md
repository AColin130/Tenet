# C++ 工程协作底线（Engineering Standards）

本文档是 **协作与质量底线**，**不是** 目录布局、不是 CMake 模板、不是「必须用 monorepo/三层 exe」。

**架构形状** 仅来自 **用户项目 ADR + baseline**；Tenet 只列出常见 **应谈清楚** 的 C++ 约定，供 G1 baseline 或 `docs/engineering.md` **勾选采纳**。

---

## 原则

1. **构建 SSOT 写进 ADR**（如 CMake 为唯一真相；IDE 工程可生成、不手改为主路径）。  
2. **工具链写进 ADR 或 baseline**（编译器最低版本、C++ 标准、生成器）。  
3. **第三方** 引入须 **license 扫过 G0 红线** + ADR 或依赖清单。  
4. **不** 在 Tenet 官方仓写业务代码；下列标准 **复制到用户项目** 后按需改。

---

## 建议 baseline 可勾选项

| 主题 | 常见约定（示例，非强制） |
|------|---------------------------|
| **语言标准** | 如 C++17/20；升级 → G2 + ADR |
| **编译警告** | 如 `/W4` 或 `-Wall -Wextra`；Treat warning as error 可选 |
| **格式化** | clang-format 配置文件路径；「全仓或按目录」 |
| **命名** | 团队一页纸：类型、函数、宏、命名空间（**不** 由 Tenet 定死） |
| **头文件** | include guard 或 `#pragma once` 团队统一 |
| **所有权/异常** | 项目级风格（如是否允许异常）写 ADR |
| **测试** | 单元测试框架 **若采用** 写 ADR；DoD 引用验收命令 |

## Testing SSOT（业务仓）

- 在 **`docs/ai-doc-map.md`** 设一行 **测试/验收**（如 `docs/testing.md`）：build target、ctest 路径、必跑用例。  
- Tenet DoD 只要求 **语义**「验收已跑」；**具体命令** 在业务 testing SSOT。  
- 专题 `.mdc` 可在改 `src/` 时懒加载并 **链 testing SSOT**（见 cursor-rules-example）。

未勾选的项 **不适用**；AI **不得** 因 Tenet 存在本文而 **默认** 引入 GoogleTest、vcpkg 等。

---

## 与 Discovery / G2 的关系

| 变更 | 路径 |
|------|------|
| 首次选型（构建、标准、主要依赖） | Discovery + ADR → G1 |
| 升级标准、换包管理、拆模块 | **G2** + ADR |

模板：[`adr-template.md`](adr-template.md)。

---

## AI 行为

- **禁止** 引用本文 **替代** 用户 baseline/ADR。  
- 用户未采纳某条标准 → **不** 强行加 clang-format、测试框架等。  
- 建议：G1 时问「baseline 要勾选哪些 engineering 底线？」并 **只写用户确认的**。  
- **新符号**：先 **grep**，再改 doc-map 所指 SSOT；不维护全量 API 清单。

---

## 相关文档

- [`adr-template.md`](adr-template.md)
- [`../process/gates/G1-baseline.md`](../process/gates/G1-baseline.md)
- [`../process/gates/G2-change.md`](../process/gates/G2-change.md)
- [`../collaboration/code-review.md`](../collaboration/code-review.md)

---

文档 v1.4 · Tenet cpp（元层，非脚手架）
