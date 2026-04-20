# 安装 Rock Agents 技能

Rock Agents 提供适用于多种 AI Agent 工具的技能（Skills），支持 Claude Code、Cursor、Copilot、Codex、OpenCode、Windsurf 等平台。

## 方式一：Skills CLI 安装（推荐）

使用 [Vercel Labs Skills](https://github.com/vercel-labs/skills) 一键安装：

```bash
# 列出可用技能
npx skills add xdlkc/rock-agents --list

# 安装所有技能到所有支持的 Agent
npx skills add xdlkc/rock-agents --all

# 安装到指定 Agent
npx skills add xdlkc/rock-agents -a claude-code    # Claude Code
npx skills add xdlkc/rock-agents -a cursor         # Cursor
npx skills add xdlkc/rock-agents -a windsurf       # Windsurf
npx skills add xdlkc/rock-agents -a opencode       # OpenCode
npx skills add xdlkc/rock-agents -a codex          # OpenAI Codex

# 安装指定技能
npx skills add xdlkc/rock-agents --skill rock-agent-debug
npx skills add xdlkc/rock-agents --skill rock-agent-sdk

# 非交互式安装（适合脚本/CI）
npx skills add xdlkc/rock-agents --all -y
```

### 支持的 Agent

| Agent | 标识符 |
|-------|--------|
| Claude Code | `claude-code` |
| Cursor | `cursor` |
| Windsurf | `windsurf` |
| OpenCode | `opencode` |
| Codex | `codex` |
| GitHub Copilot | `github-copilot` |
| Cline | `cline` |
| Goose | `goose` |
| Replit | `replit` |
| Kimi CLI | `kimi-cli` |
| Qwen Code | `qwen-code` |

## 方式二：手动复制

克隆仓库后手动复制技能文件到对应工具的技能目录：

```bash
git clone git@github.com:xdlkc/rock-agents.git ~/Code/rock-agents
```

### 各工具技能目录

| 工具 | 技能目录 |
|------|----------|
| Claude Code | `~/.claude/skills/` |
| Cursor | `~/.cursor/skills/` |
| Windsurf | `~/.codeium/windsurf/skills/` |
| Codex | `~/.codex/skills/` |
| OpenCode | `~/.opencode/skills/` |

复制示例：

```bash
# Claude Code
cp -r ~/Code/rock-agents/skills/rock-agent-debug ~/.claude/skills/
cp -r ~/Code/rock-agents/skills/rock-agent-sdk ~/.claude/skills/

# Cursor
cp -r ~/Code/rock-agents/skills/rock-agent-debug ~/.cursor/skills/
```

## 可用技能

| 技能 | 说明 |
|------|------|
| `rock-agent-debug` | 排查 ROCK 沙箱中 Harbor Job 和 Bash Job 的状态与问题 |
| `rock-agent-sdk` | ROCK Agent SDK 开发指南 |

## 验证安装

启动对应工具，检查技能列表：

- **Claude Code**: `/skills list`
- **Cursor**: Skills 面板或命令面板
- **其他工具**: 参考各工具文档

## 更新

```bash
# 使用 CLI 更新
npx skills update rock-agent-debug
npx skills update rock-agent-sdk

# 或重新添加
npx skills add xdlkc/rock-agents --all -y
```

## 卸载

```bash
npx skills remove rock-agent-debug
npx skills remove rock-agent-sdk
```

或手动删除技能目录：

```bash
rm -rf ~/.claude/skills/rock-agent-debug
rm -rf ~/.claude/skills/rock-agent-sdk
```
