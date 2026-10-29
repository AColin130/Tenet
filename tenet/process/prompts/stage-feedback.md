# 阶段结束 · 标准反馈

AI 在 **G0 落盘、Discovery 里程碑、EXIT 确认、G1 通过、Delivery 单项完成** 后，须先发对应反馈块，**等待用户回复** 后再进入下一阶段或继续大批量生成。完整规则见 [`../discovery/facilitation.md`](../discovery/facilitation.md)。

用户也可 **复制** 下列块主动要求 AI 停步复盘。

---

## G0 完成后

```text
【Tenet · G0 阶段停步】请先不要进入 G1 / 不要批量写工程树。

请回复下面 4 点（可逐条）：
1. charter 里有没有漏的需求、错的边界或非目标？
2. 合规 / 许可证还要补充什么红线？
3. 有没有「现在只记 backlog、不改 scope」的想法？
4. 下一步：回复「进入 Discovery」；或说明要改 G0 的内容。
```

---

## Discovery 中期（可选）

```text
【Tenet · Discovery 同步】当前不做 G1 落盘。

请根据 exit-criteria 自检进度，并回复：
1. 已满足的出口项（附 docs 链接）：
2. 仍缺哪几项：
3. 是否需要 disposable spike？是 / 否；若是要验证什么：
4. 有无新风险或 scope 漂移？有则描述，可能需回 G0。
```

---

## Discovery 出口 / 申请 G1 前

```text
【Tenet · Discovery 出口停步】请对照 exit-criteria，不要默认 G1 已通过。

请回复：
1. EXIT 确认是否已写入 docs/discovery/EXIT.md（或等价）？
2. ADR 与 G0 是否仍一致？
3. 还要在 Discovery 补什么？没有则回复「申请 G1」并附 baseline 草案要点。
4. 有无未关闭的 spike / disposable 目录？
```

---

## G1 通过后

```text
【Tenet · G1 阶段停步】baseline 已批准；结构性变更须 ADR。

请回复：
1. Delivery 用 Scrum 还是 Kanban（若 baseline 已写则确认）？
2. 第一个 Delivery 增量要什么验收（如 exit 0、测试名）？
3. backlog 里还有没有必须先说清的约束？
4. 回复「开始 Delivery」并指定第一项；或说明要改 baseline（须 ADR）。
```

---

## Delivery 单项完成后

```text
【Tenet · Delivery 增量停步】本项已按 baseline/ADR 验收。

请回复：
1. 验收结果是否符合预期？问题：
2. 是否暴露要用 ADR 的架构/工具链问题？
3. 下一项做什么，或是否暂停？
4. 其他需求或优化（可进 backlog，不必改 G0）：
```

---

## 可选 · 方案压测（非默认 Tenet 关口）

重大方案已定稿、想挑刺时，用户 **自行** 使用 Grill 等 skill；**不替代** 上列停步。

```text
【可选 · 压测】请对我上面的方案做 Grill：列假设、风险、我漏掉的边界。不要开始写代码。
```
