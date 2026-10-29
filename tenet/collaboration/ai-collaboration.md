# AI 协作约定

与 [`../AGENTS.md`](../AGENTS.md)、[`../process/discovery/facilitation.md`](../process/discovery/facilitation.md) 一并使用。

---

## 默认回复格式

| 顺序 | 内容 | 上限建议 |
|------|------|----------|
| 1 | 当前 Tenet **阶段** + 本请求 **做或不做** | 2 句 |
| 2 | **一步**：一个模板链接或全文粘贴，或一道 ABCD | 1 块 |
| 3 | 细节、列表、代码 | 用户追问后再展开 |

**禁止** 默认用长篇教程代替「下一步可复制动作」。

---

## 用户不知道说什么时

1. 判断阶段（G0 / Discovery / G1 前 / Delivery）。  
2. 从 [`../process/prompts/`](../process/prompts/README.md) 选 **一个** 模板 **贴出全文**。  
3. 说明：「请复制上面块，改 `[ ]` / `___` 后发回。」

---

## 多工具（Cursor、Claude Code、Copilot 等）

- 流程 **只认** `tenet/AGENTS.md`；对话开始应 @ 该文件。  
- 不要在各工具里 **另写一套** Tenet 流程摘要（易与 SSOT 分叉）。  
- 业务仓根 `AGENTS.md` 只放 **本地事实** + 指向 tenet。

---

## 阶段停步

见 facilitation **阶段停步协议**；完成 G0 / Discovery 节点 / G1 / Delivery 单项后 **必停**，用 [`../process/prompts/stage-feedback.md`](../process/prompts/stage-feedback.md)。

---

## 可选压测

用户明确要求挑刺方案时，可用 Grill 等；**不** 作为 G0/G1 默认步骤。

---

文档 v1.1 · Tenet collaboration
