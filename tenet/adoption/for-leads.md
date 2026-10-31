# 给负责人 / Tech Lead（For Leads）

面向 **决定团队怎么裁剪 Tenet** 的人：EM、Tech Lead、开源维护者。  
Tenet **默认** 参照 20+ 人习惯；小团队 **应删仪式、保留关口**。

---

## 不可删（删了 AI 易乱建）

| 保留 | 原因 |
|------|------|
| **G0 charter** | 边界与非目标 |
| **Discovery exit + G1** | 正式落盘许可 |
| **tenet/AGENTS SSOT** | 多工具一致 |
| **G2（有结构性变更时）** | ADR + baseline 升版 |
| **Delivery 停步 + 模板** | 用户知道下一步 |

---

## 可裁剪

| 可减 | 做法 |
|------|------|
| Scrum 仪式 | 改 Kanban + delivery-item 模板 |
| 多人 Review | 1 人 + 自检清单 + 停步（见 [`../collaboration/code-review.md`](../collaboration/code-review.md)） |
| 长篇 discovery 文档 | 合并为 scope + 1 份 ADR；exit-criteria **仍逐条满足** |
| Submodule | **拷贝 tenet/**（见 [`for-newcomers.md`](for-newcomers.md)） |

---

## 推荐裁剪档位

| 档位 | 谁 | 流程 |
|------|-----|------|
| **A · 个人 + AI** | 1 人 | G0 → 短 Discovery → G1 → Kanban + DoD 简化 |
| **B · 小团队** | 2–8 | 全双轨；Review 轮流；G2 书面 |
| **C · 大团队** | 20+ | 全文档 + roles + 合并门禁 + 定期集成演示 |

在 **baseline §5** 写「本仓采用档位 B」即可。

---

## Tenet 官方仓 vs 业务仓

| 仓库 | 负责人做什么 |
|------|----------------|
| **Tenet（D:\Tenet / GitHub）** | 只改 `tenet/**` 元文档；**无业务 C++**；Git 约定见根目录 **[`CONTRIBUTING.md`](../../CONTRIBUTING.md)** |
| **业务仓** | 维护 charter/baseline/ADR；**拷贝或更新 tenet/**；Git 约定 **自选**（可复制 [`../collaboration/commit-conventions.md`](../collaboration/commit-conventions.md)） |

C++ 测试仅 **验证 Tenet 能用**（如桌面试点），不是 Tenet 产品交付物。

---

## 引入 Tenet 到现有老项目

1. 拷贝 `tenet/` + LICENSE  
2. 补 **追溯 G0**（可写「retro charter」注明日期）  
3. 当前架构 → **ADR 已接受** + **baseline v1**（retro G1）  
4. 此后变更走 G2  

不必重写历史，但 **须** 有一次 baseline 记录。

---

## v1.4 文档全集（维护参考）

流程、教练、Delivery、G2、ADR 模板、roles、code-review、engineering 底线、newcomers/leads — 见 [`../process/OVERVIEW.md`](../process/OVERVIEW.md) 版本节。

后续增强 **仅 Issue 驱动**，避免文档膨胀。

---

## 相关文档

- [`for-newcomers.md`](for-newcomers.md)
- [`../collaboration/roles.md`](../collaboration/roles.md)
- [`../process/OVERVIEW.md`](../process/OVERVIEW.md)
- [`../collaboration/commit-conventions.md`](../collaboration/commit-conventions.md)（业务仓可选）
- [`../../CONTRIBUTING.md`](../../CONTRIBUTING.md)（官方仓 Git）

---

文档 v1.4 · Tenet adoption
