---
sidebar_position: 6
---

# Claude Code

**Claude Code** is a command-line tool for agentic programming developed by Anthropic. It enables developers to interact with Claude AI through a terminal interface, facilitating intelligent programming assistance including code generation, debugging, refactoring, and more.

## Installation

### Install npm

```shell
sudo apt install npm
```

### Install Claude Code

```shell
sudo npm i --registry=http://nexus.bianbu.xyz/repository/npmproxy/ -g @anthropic-ai/claude-code
```

Verify installation:

```shell
claude --version
```

## Configuration

### Set Environment Variables

**Note**: When creating an API Token, you need to select the **claude** group in the group selection.

```shell
cat >> ~/.bashrc << 'EOF'
export ANTHROPIC_BASE_URL="provider_url"
export ANTHROPIC_AUTH_TOKEN="generated_api_key"
EOF
source ~/.bashrc
```

### Configure API Key Auto-approval

```shell
(cat ~/.claude.json 2>/dev/null || echo 'null') | jq --arg key "${ANTHROPIC_API_KEY: -20}" '(. // {}) | .customApiKeyResponses.approved |= ([.[]?, $key] | unique)' > ~/.claude.json.tmp && mv ~/.claude.json.tmp ~/.claude.json
```

## Usage

Start an interactive Claude Code session:

```shell
claude
```

Switch models and usage:
![](../static/claude-use.png)


In the interactive session, you can:
- Ask programming questions
- Request code generation and optimization
- Perform code debugging and refactoring
- Get technical advice and best practices

Type `/exit` to exit the session.