---
---

import useDocusaurusContext from '@docusaurus/useDocusaurusContext';

import { DISCORD_URL } from '@site/src/constants.ts'

# 常见问题解答

本页面回答了一些关于 Kilo Code 的常见问题。

## 一般问题

### 什么是 Kilo Code？

Kilo Code 是一个用于 Visual Studio Code 的开源 AI 代理扩展。它通过生成代码、自动化任务和提供建议来帮助你更高效地编写代码。

### Kilo Code 是如何工作的？

Kilo Code 使用大型语言模型（LLMs）来理解你的请求并将其转化为操作。它可以：

- 读取和写入项目中的文件。
- 在 VS Code 终端中执行命令。
- 执行网页浏览（如果启用）。
- 通过模型上下文协议（MCP）使用外部工具。

你通过聊天界面与 Kilo Code 交互，在其中提供指令并审查/批准其建议的操作。

### Kilo Code 能做什么？

Kilo Code 可以帮助你完成各种编码任务，包括：

- 从自然语言描述生成代码。
- 重构现有代码。
- 修复错误。
- 编写文档。
- 解释代码。
- 回答关于代码库的问题。
- 自动化重复性任务。
- 创建新文件和项目。

### Kilo Code 是免费使用的吗？

Kilo Code 扩展本身是免费且开源的。如果你想赚取一些积分，可以加入我们的 <a href={DISCORD_URL} target='_blank'>Discord</a>，我们有时会有促销活动！

之后，你可以添加信用卡购买更多代币（通过 Stripe 安全处理。我们的定价与 Anthropic 的 API 费率完全一致。我们不收取任何费用，无论是按代币还是按充值。未来我们将添加更多 LLM 提供商。

或者，你可以“自己提供 API”（如 [Anthropic](providers/anthropic)、[OpenAI](providers/openai)、[OpenRouter](providers/openrouter)、[Requesty](providers/requesty) 等）来使用其 AI 功能。这些提供商通常根据处理的代币数量收取 API 使用费。你需要创建账户并从所选提供商处获取 API 密钥。详情请参见 [设置你的第一个 AI 提供商](getting-started/connecting-api-provider)。

### 使用 Kilo Code 有哪些风险？

Kilo Code 是一个强大的工具，使用时需要负责任。以下是一些需要注意的事项：

- **Kilo Code 可能会出错。** 在批准之前，请务必仔细审查 Kilo Code 建议的更改。
- **Kilo Code 可以执行命令。** 允许 Kilo Code 运行命令时要非常谨慎，特别是如果你启用了自动批准。
- **Kilo Code 可以访问互联网。** 如果你使用支持网页浏览的提供商，请注意 Kilo Code 可能会访问敏感信息。

## 设置与安装

### 如何安装 Kilo Code？

请参阅 [安装指南](/getting-started/installing) 获取详细说明。

### 支持哪些 API 提供商？

Kilo Code 支持多种 API 提供商，包括：

- [Anthropic (Claude)](/providers/kilocode)
- [Anthropic (Claude)](/providers/anthropic)
- [OpenAI](/providers/openai)
- [OpenRouter](/providers/openrouter)
- [Google Gemini](/providers/gemini)
- [Glama](/providers/glama)
- [AWS Bedrock](/providers/bedrock)
- [GCP Vertex AI](/providers/vertex)
- [Ollama](/providers/ollama)
- [LM Studio](/providers/lmstudio)
- [DeepSeek](/providers/deepseek)
- [Mistral](/providers/mistral)
- [Unbound](/providers/unbound)
- [Requesty](/providers/requesty)
- [VS Code 语言模型 API](/providers/vscode-lm)

### 如何获取 API 密钥？

每个 API 提供商都有自己的获取 API 密钥的过程。请参阅 [设置你的第一个 AI 提供商](/getting-started/connecting-api-provider) 获取每个提供商的相关文档链接。

### 我可以将 Kilo Code 与本地模型一起使用吗？

是的，Kilo Code 支持使用 [Ollama](/providers/ollama) 和 [LM Studio](/providers/lmstudio) 在本地运行模型。请参阅 [使用本地模型](/advanced-usage/local-models) 获取说明。

## 使用方法

### 如何开始新任务？

打开 Kilo Code 面板 (<img src="/docs/img/kilo-v1.svg" width="12" />) 并在聊天框中输入你的任务。明确具体地说明你希望 Kilo Code 做什么。请参阅 [聊天界面](/basic-usage/the-chat-interface) 获取最佳实践。

### 什么是 Kilo Code 中的模式？

[模式](/basic-usage/using-modes) 是 Kilo Code 可以采用的不同角色，每个角色都有特定的焦点和能力集。内置模式包括：

- **Code：** 用于通用编码任务。
- **Architect：** 用于规划和技术领导。
- **Ask：** 用于回答问题和提供信息。
- **Debug：** 用于系统性问题诊断。
  你还可以创建 [自定义模式](/features/custom-modes)。

### 如何在模式之间切换？

使用聊天输入区域的下拉菜单选择不同的模式，或使用 [/](file:///Users/john/GolandProjects/kilo-docs/LICENSE) 命令切换到特定模式。

### 什么是工具以及如何使用它们？

[工具](/basic-usage/how-tools-work) 是 Kilo Code 与你的系统交互的方式。Kilo Code 会自动选择并使用适当的工具来完成你的任务。你无需直接调用工具。每次工具使用时都会提示你批准或拒绝。

### 什么是上下文提及？

[上下文提及](/basic-usage/context-mentions) 是向 Kilo Code 提供项目特定信息的方式，如文件、文件夹或问题。使用 "@" 符号后跟你想要提及的项目（例如，`@/src/file.ts`，`@problems`）。

### Kilo Code 可以访问互联网吗？

是的，如果你使用支持网页浏览的模型提供商。请注意允许此功能的安全影响。

### Kilo Code 可以在我的终端中运行命令吗？

是的，Kilo Code 可以在你的 VS Code 终端中执行命令。除非你启用了命令的自动批准，否则每次执行命令前都会提示你批准。对于自动批准命令要极其谨慎。如果你在终端命令方面遇到问题，请参阅 [Shell 集成指南](/features/shell-integration) 进行故障排除。

### 如何向 Kilo Code 提供反馈？

你可以通过批准或拒绝 Kilo Code 建议的操作来提供反馈。你还可以使用反馈字段提供额外反馈。

### 我可以自定义 Kilo Code 的行为吗？

是的，你可以通过以下几种方式自定义 Kilo Code：

- **自定义指令：** 提供适用于所有模式的一般指令，或特定模式的指令。
- **自定义模式：** 创建具有定制提示和工具权限的自己的模式。
- **`.clinerules` 文件：** 在项目中创建 `.clinerules` 文件以提供额外指导。
- **设置：** 调整各种设置，如自动批准、差异编辑等。

### Kilo Code 有自动批准设置吗？

是的，Kilo Code 有一些启用后会自动批准操作的设置。了解更多 [这里](/features/auto-approving-actions)。

## 高级功能

### 我可以离线使用 Kilo Code 吗？

是的，如果你使用 [本地模型](/advanced-usage/local-models)。

### 什么是 MCP（模型上下文协议）？

[MCP](/features/mcp/overview) 是一种允许 Kilo Code 与外部服务器通信的协议，通过自定义工具和资源扩展其功能。

### 我可以创建自己的 MCP 服务器吗？

是的，你可以创建自己的 MCP 服务器来为 Kilo Code 添加自定义功能。详情请参阅 [MCP 文档](https://github.com/modelcontextprotocol)。

## 故障排除

### Kilo Code 没有响应。我该怎么办？

- 确保你的 API 密钥正确且未过期。
- 检查你的互联网连接。
- 检查你选择的 API 提供商的状态。
- 尝试重启 VS Code。
- 如果问题仍然存在，请在 [GitHub](https://github.com/Kilo-Org/kilocode/issues) 或 [Discord](https://kilocode.ai/discord) 上报告问题。

### 我看到错误消息。这是什么意思？

错误消息应该提供有关问题的一些信息。如果你不确定如何解决，请在社区论坛寻求帮助。

### Kilo Code 做了我不想要的更改。如何撤销？

Kilo Code 使用 VS Code 的内置文件编辑功能。你可以使用标准的“撤销”命令（Ctrl/Cmd + Z）来撤销更改。此外，如果启用了实验性检查点，Kilo 可以撤销对文件所做的更改。

### 如何报告错误或建议功能？

请在 Kilo Code [问题页面](https://github.com/Kilo-Org/kilocode/issues) 和 [功能请求页面](https://github.com/Kilo-Org/kilocode/discussions/categories/ideas) 上报告错误或建议功能。
