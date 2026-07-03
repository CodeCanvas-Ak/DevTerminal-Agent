# DevTerminal Agent — 终端 AI 编程助手

![Python Version](https://img.shields.io/badge/python-3.11+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Version](https://img.shields.io/badge/version-0.2.0-orange.svg)
![GitHub Repo stars](https://img.shields.io/github/stars/CodeCanvas-Ak/DevTerminal-Agent?style=social)

轻量级终端 AI 编码助手，基于 ReAct 与 Plan Mode 双模式驱动 LLM 自主完成编程任务。

## 特性

- 🌟 **双模式驱动**: ReAct 实时交互 + Plan Mode 计划模式
- 🔧 **分层架构**: 交互、引擎、工具、记忆、安全五层架构
- 🤖 **多协议支持**: Anthropic、OpenAI、OpenAI-compatible 协议
- 🛠️ **MCP 扩展**: 支持 Model Context Protocol 工具扩展
- 📦 **技能系统**: 内置 Skill 技能包
- 🧠 **跨会话记忆**: 持久化记忆管理
- 👥 **多 Agent 协作**: 支持多 Agent 并行协作

## 安装

### 前置要求

- Python 3.11+
- pip / uv

### 使用 uv（推荐）

```bash
uv pip install devterminal
```

### 使用 pip

```bash
pip install devterminal
```

## 快速开始

### 1. 配置

首先创建配置目录和配置文件：

```bash
mkdir -p ~/.devterminal
cp .devterminal/config.yaml.example ~/.devterminal/config.yaml
```

编辑配置文件，填入你的 API 密钥：

```yaml
providers:
  - name: claude
    protocol: anthropic
    base_url: https://api.anthropic.com
    model: claude-3-5-sonnet-20241022
    api_key: "your-api-key-here"  # 或设置环境变量 ANTHROPIC_API_KEY
```

### 2. 运行

```bash
devterminal
```

## 配置说明

### 环境变量

- `ANTHROPIC_API_KEY`: Anthropic API 密钥
- `OPENAI_API_KEY`: OpenAI API 密钥

### 配置文件

配置文件位置：
- `~/.devterminal/config.yaml`: 全局配置
- `.devterminal/config.yaml`: 项目级配置
- `.devterminal/config.local.yaml`: 本地覆盖配置

### 权限模式

- `default`: 默认模式，每次编辑需要确认
- `acceptEdits`: 自动接受编辑
- `plan`: 计划模式，先生成计划再执行
- `bypassPermissions`: 绕过所有权限检查
- `custom`: 自定义权限
- `dontAsk`: 不询问，直接执行

## 开发

### 安装开发依赖

```bash
uv sync --dev
```

### 运行测试

```bash
uv run pytest
```

## 架构

```
devterminal/
├── agents/          # Agent 定义与管理
├── commands/        # 命令系统
├── context/         # 上下文管理
├── filehistory/     # 文件历史
├── hooks/           # 钩子系统
├── mcp/             # MCP 协议支持
├── memory/          # 记忆系统
├── permissions/     # 权限管理
├── skills/          # 技能系统
├── teams/           # 团队协作
├── tools/           # 工具集
└── worktree/        # 工作区管理
```

## 许可证

[待补充]

## 贡献

欢迎贡献！请提交 Issue 和 Pull Request。
