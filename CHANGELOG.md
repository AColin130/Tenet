# Changelog

本文件记录 **Tenet 官方仓**（元层文档）的版本摘要。格式 loosely 基于 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.1.0/)。  
业务 C++ 仓变更 **不** 写在此文件。

## [Unreleased]

### Added

- **Agent 自主度三条**（`tenet/AGENTS.md`）：同一纠正必须升格到 Tier 0 或 ADR；AI 声称完成前自己跑验收；验收尚未无人跑通时不扩大并行，自动合并默认关闭。细则见 governance-tier、DoD、code-review、ai-collaboration。
- **教练层防越挖**：意图→默认阶段、单层推进、G0 黑名单、首次想法停步；模板 `g0-idea-only.md`、`discovery-tech-compare.md`（`facilitation.md`、`ai-collaboration.md`、`stage-feedback.md`）。

## [1.5.0] - 2026-10-31

### Added

- **WeCarver 对照采纳（元层/模板）**：`governance-tier-template.md`、`adoption/templates/*`（ai-doc-map、llms、PR、journal、mistake）、`grill-doc-default.md`、`cursor-rules-example/`、`integration-backlog.md`（closed）
- 根 `llms.txt`（官方仓入口）；`ai-collaboration.md` 扩展（cite SSOT、读序封顶、子 Agent、Skills）
- `project-vs-tenet.md`：项目 `docs/` vs `tenet/`、backlog 约定
- `.github/` Issue/PR 模板；`CHANGELOG.md`；`g2-request`；`scrum-minimal` / `kanban-minimal`
- `docs/releases/v1.5.0.md`

### Changed

- `OVERVIEW` / `for-leads` / `code-review` / `engineering-standards` / `facilitation` 与 v1.5 行为对齐

## [1.4.0] - 2026-10-31

### Added

- `CONTRIBUTING.md`：官方仓 commit **单语** + Conventional 前缀约定
- `tenet/collaboration/commit-conventions.md`（业务仓可选）
- `tenet/collaboration/roles.md`、`code-review.md`
- `tenet/cpp/engineering-standards.md`（协作底线，非脚手架）
- `tenet/adoption/for-leads.md`
- `tenet/process/gates/G2-change.md`
- `tenet/cpp/adr-template.md`
- `docs/releases/v1.4.0.md`

### Changed

- `tenet/AGENTS.md` 文档地图与 G2 引用
- README 流程图 G2 表述、文档地图

## [1.3.0] - 2026-10-29

### Added

- G2 关口、ADR 模板、for-newcomers 拷贝 `tenet/` 单仓说明

## [1.2.0] - 2026-10-29

### Added

- `definition-of-done.md`、`choose-scrum-kanban.md`
- `for-newcomers.md`

## [1.1.0] - 2026-10-29

### Added

- `facilitation.md`、阶段停步协议
- `process/prompts/*` 可复制模板
- `ai-collaboration.md`

## [1.0.0] - 2026-10-29

### Added

- 五件套：AGENTS、OVERVIEW、G0、G1、exit-criteria
- README（顶英下中）、MIT LICENSE

[1.5.0]: https://github.com/AColin130/Tenet/releases/tag/v1.5.0
[1.4.0]: https://github.com/AColin130/Tenet/releases/tag/v1.4.0
[1.3.0]: https://github.com/AColin130/Tenet/compare/v1.0.0...v1.4.0
[1.2.0]: https://github.com/AColin130/Tenet/compare/v1.0.0...v1.4.0
[1.1.0]: https://github.com/AColin130/Tenet/compare/v1.0.0...v1.4.0
[1.0.0]: https://github.com/AColin130/Tenet/releases/tag/v1.0.0
