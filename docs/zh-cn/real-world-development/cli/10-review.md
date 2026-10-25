---
title: "第 10 课 - 总结和后续步骤"
description: "回顾 Copilot CLI 工作流、两个拉取请求、可复用的自定义配置和更多资源。"
authors:
  - geektrainer
lastUpdated: 2026-09-29
---

你在 Tailspin Toys 的连续工作流中使用了 GitHub Copilot CLI。你完成了以下工作：

- 准备 Codespace、安装 Copilot CLI、探索项目，并找到预置的筛选问题。
- 添加星级评分，在转发的浏览器中检查结果，并手动合并第一个拉取请求 (PR)。
- 从筛选问题开始，在 Plan 模式中定义方案，在 Autopilot 模式中实现，并在 Interactive 模式中审查。
- 使用自定义说明指导智能体，然后自定义现有的 `quality-checks` 技能，并用它运行单元测试、lint 和类型检查。
- 添加 Playwright Model Context Protocol (MCP) 服务器，并在真实浏览器中探索筛选功能。
- 创建并选择质量保证 (QA) 自定义智能体，以评估需求、覆盖范围、技能结果和浏览器证据。
- 审查完整的筛选更改，并授权对筛选 PR 执行 Agent Merge。
- 探索用于上下文、模型、共享以及可选云端委派的斜杠命令。

## 交付成果

本研讨会有两个 PR 里程碑，分别位于从更新后的 `main` 创建的独立分支上：

1. **星级评分：** 在游戏卡片上显示现有的 `starRating`，并明确显示未评分状态。
2. **筛选和质量工作流：** 实现筛选、更新说明并将其应用于此功能、自定义 `quality-checks` 报告、创建 QA 配置，并添加相关测试。

从规划筛选到创建 PR，你一直使用同一会话和分支。为简化研讨会，我们将这些工作合并到一个 PR 中。

## 不同的验证方式

你通过多种方式检查代码：自动化测试、自己在浏览器中检查，以及 Copilot 通过 MCP 探索浏览器。`quality-checks` 技能运行单元测试、lint 和类型检查，并以新格式报告结果。创建 PR 之前，QA 将这些结果与需求和测试覆盖率审查结合起来。

新增测试应填补实际缺口；QA 运行后不需要增加测试也可能是正确结果。授权合并前请审查代码和证据，并在更改后更新受影响的证据。

## 最佳实践

提供给 Copilot 的上下文和工具会影响它的工作。本研讨会中，你更新了说明、自定义技能、创建 QA 配置并设置 MCP 服务器。可以在不同会话中重复使用这些自定义配置，并根据团队需求进行调整。说明用于设定标准，技能用于描述可重复执行的任务，自定义智能体用于定义专门角色，MCP 服务器用于连接外部工具。请检查实际更改和工具结果，而不仅仅是智能体的摘要。

根据任务选择**模式和模型**。在构建前规划方案时使用 **Plan**，需要持续参与具体更改时使用 **Interactive**，处理范围明确的任务时使用 **Autopilot**。常规编辑可选择速度更快的模型，复杂任务则选择能力更强的模型。

上下文与基础设施同样重要。清楚说明要构建*什么*、*为什么*构建以及*如何*构建，会显著影响输出。

## 进一步探索

你已完成核心工作流。还可以了解 Copilot CLI 的其他功能：

- 使用 `/review` 请求代码审查智能体分析更改。
- 使用 `/rubber-duck` 讨论问题并获得其他视角。
- 使用 `/fleet` 并行协调相互独立的子任务。
- 使用 `/worktree` 隔离其他任务。
- 使用 `/delegate` 将任务发送给 Copilot 云智能体。

## 后续步骤

熟练使用任何工具的最佳方法就是持续使用。可以将它用于生产代码、个人项目，或那个想了很多年却一直没开始制作的小应用。与团队分享经验，也从团队成员的经验中学习。和往常一样，也要继续探索文档。

如果要从终端扩展 Tailspin Toys，请继续学习可选的 [Foundry Backer Concierge 系列][foundry]。如需比较其他环境，请探索 [VS Code 研讨会][vscode]、[GitHub Copilot app 研讨会][app]或 [Copilot 云智能体研讨会][cloud]。

## 资源

- [关于 GitHub Copilot CLI][about-cli]
- [Copilot CLI 命令参考][cli-reference]
- [自定义 Copilot CLI][customize-cli]
- [使用 Copilot CLI 管理拉取请求][manage-prs]

[previous-lesson]: ../9-cli-power-tools/
[foundry]: ../8-foundry-agent/
[vscode]: ../../vscode/
[app]: ../../app/
[cloud]: ../../cloud/
[about-cli]: https://docs.github.com/copilot/concepts/agents/about-copilot-cli
[cli-reference]: https://docs.github.com/copilot/reference/copilot-cli-reference/cli-command-reference
[customize-cli]: https://docs.github.com/copilot/how-tos/copilot-cli/customize-copilot
[manage-prs]: https://docs.github.com/copilot/how-tos/copilot-cli/use-copilot-cli/manage-pull-requests
