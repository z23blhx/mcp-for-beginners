![MCP for Beginners](./images/mcp-beginners.png)

# 🚀 MCP 初学者教程（简体中文版入口）

本仓库是 [Microsoft MCP for Beginners](https://github.com/microsoft/mcp-for-beginners) 的 Fork。

仓库本身已经包含较完整的 **简体中文翻译**，位于：

👉 **[进入完整简体中文课程](./translations/zh-CN/README.md)**

英文原版内容仍保留在仓库原有目录中，便于对照学习；本页面只作为中文学习入口，不重复复制所有翻译文件，这样以后从上游同步更新时更容易维护。

> 中文内容由上游项目的翻译流程生成。涉及 MCP 规范、API、版本变化或重要技术细节时，建议同时参考英文原文和官方 MCP 文档。

## 📚 中文课程目录

| 模块 | 中文主题 | 中文课程 |
|---|---|---|
| 00 | MCP 简介 | [开始学习](./translations/zh-CN/00-Introduction/README.md) |
| 01 | MCP 核心概念 | [开始学习](./translations/zh-CN/01-CoreConcepts/README.md) |
| 02 | MCP 安全 | [开始学习](./translations/zh-CN/02-Security/README.md) |
| 03 | MCP 入门与环境搭建 | [开始学习](./translations/zh-CN/03-GettingStarted/README.md) |
| 04 | 实践实现 | [开始学习](./translations/zh-CN/04-PracticalImplementation/README.md) |
| 05 | 高级主题 | [开始学习](./translations/zh-CN/05-AdvancedTopics/README.md) |
| 06 | 社区贡献 | [开始学习](./translations/zh-CN/06-CommunityContributions/README.md) |
| 07 | 早期实践经验 | [开始学习](./translations/zh-CN/07-LessonsfromEarlyAdoption/README.md) |
| 08 | 最佳实践 | [开始学习](./translations/zh-CN/08-BestPractices/README.md) |
| 09 | 案例研究 | [开始学习](./translations/zh-CN/09-CaseStudy/README.md) |
| 10 | 使用 AI Toolkit 构建 MCP Server | [开始学习](./translations/zh-CN/10-StreamliningAIWorkflowsBuildingAnMCPServerWithAIToolkit/README.md) |
| 11 | MCP Server 实战实验 | [开始学习](./translations/zh-CN/11-MCPServerHandsOnLabs/README.md) |
| 12 | MCP 工具生态 | [开始学习](./translations/zh-CN/12-tooling/README.md) |

## 🎯 初学者推荐学习顺序

如果你第一次学习 MCP，不建议一开始把整个仓库全部看完。推荐顺序：

1. **00 - MCP 简介**：先理解 MCP 解决什么问题。
2. **01 - 核心概念**：重点理解 Host、Client、Server、Tool、Resource、Prompt、Transport。
3. **03 - 入门**：动手创建第一个 MCP Server。
4. **03 / First Server**：学习如何注册和运行 Tool。
5. **03 / Client**：理解 Client 如何发现和调用 Server 的能力。
6. **03 / Client with LLM**：理解 LLM 如何根据用户问题选择 Tool。
7. **03 / Testing 与 MCP Inspector**：学习测试 Tool、参数 Schema 和返回结果。
8. **08 - 最佳实践**：在掌握基本流程后再学习设计与工程实践。

## 🧠 MCP 可以先这样理解

```text
用户
  ↓
AI 应用 / MCP Host
  ↓
LLM 判断是否需要工具
  ↓
MCP Client
  ↓
MCP Server
  ↓
Tools / Resources / 外部 API / 数据库
```

MCP 的核心目的，是为 AI 应用连接外部工具和数据源提供统一、标准化的接口。

## 🐍 Python 初学者建议

如果你主要使用 Python，可以优先学习仓库中的 Python 示例。一个最小 MCP Server 通常类似：

```python
from mcp.server.fastmcp import FastMCP

mcp = FastMCP("Demo MCP Server")

@mcp.tool()
def add(a: float, b: float) -> float:
    """将两个数字相加。"""
    return a + b

if __name__ == "__main__":
    mcp.run()
```

学习时重点关注：

- `FastMCP(...)`：创建 MCP Server。
- `@mcp.tool()`：把普通 Python 函数暴露成 MCP Tool。
- 函数参数与类型：会影响 Tool 的参数 Schema。
- docstring / description：会帮助 LLM 理解这个 Tool 什么时候应该被调用。
- `mcp.run()`：启动 MCP Server。

## 💻 克隆你的 Fork

```powershell
git clone https://github.com/z23blhx/mcp-for-beginners.git
cd mcp-for-beginners
code .
```

仓库较大，并包含多语言翻译。如果只需要英文源码而不需要翻译文件，可以参考上游项目的 sparse checkout 方法；如果主要使用本中文版学习，则应保留 `translations/zh-CN`。

## 🔗 重要链接

- [完整简体中文课程](./translations/zh-CN/README.md)
- [Microsoft 原始仓库](https://github.com/microsoft/mcp-for-beginners)
- [Model Context Protocol 官方文档](https://modelcontextprotocol.io/)
- [MCP Python SDK](https://github.com/modelcontextprotocol/python-sdk)
- [MCP TypeScript SDK](https://github.com/modelcontextprotocol/typescript-sdk)

## 📄 说明

本 Fork 主要用于个人学习和中文阅读。原项目版权、许可证及贡献规则以 Microsoft 上游仓库中的相关文件为准。
