# rock-agents

ROCK 平台 AI Agent 技能插件库，为 Claude Code 等 AI 工具提供针对 ROCK 平台的专属技能。

**ROCK (Reinforcement Open Construction Kit)** 是阿里巴巴开发的沙箱环境管理框架，专为 Agentic 强化学习场景设计。**Harbor** 是运行在 ROCK 沙箱中的 Agent Benchmark 评测框架。

## 结构

```
rock-agents/
├── skills/                         # Skills 目录（兼容 npx skills add）
│   ├── rock-agent-debug ->         # 软链到 plugins
│   └── rock-agent-sdk ->           # 软链到 plugins
├── plugins/                        # Claude Code Plugin 目录
│   ├── rock-agent/                 # Harbor / Bash Job 排查
│   │   ├── plugin.json
│   │   └── skills/rock-agent-debug/
│   └── rock-agent-sdk/             # Agent SDK 开发指南
│       ├── plugin.json
│       └── skills/rock-agent-sdk/
├── marketplace/                    # Marketplace 索引
│   └── marketplace.json
└── docs/
    ├── installation.md             # 安装指南
    └── plugin-spec.md              # 插件规范
```

## 安装技能

详见 [安装指南](docs/installation.md)。

**快速安装（支持 Claude Code、Cursor、Windsurf、Codex、OpenCode 等）：**

```bash
npx skills add xdlkc/rock-agents --all
```

**Claude Code 用户可通过 Plugin Marketplace 安装：**

```
/plugin marketplace add xdlkc/rock-agents
/plugin install rock-agent@rock-agents
```

## 开发插件

参考 [插件规范](docs/plugin-spec.md) 创建新插件。

每个插件包含：
- `plugin.json` — 插件元数据（名称、版本、描述、作者）
- `hooks/hooks.json` — 钩子配置（可选）
- `skills/<skill-name>/SKILL.md` — 技能文件

## 已有插件

| 插件 | 描述 | 技能数 |
|------|------|--------|
| `rock-agent-sdk` | ROCK Agent SDK 开发指南 | 1 |
| `rock-agent` | Harbor / Bash Job 运行分析与调试 | 1 |

### 插件详情

**rock-agent-sdk**
| 技能 | 说明 |
|------|------|
| `rock-agent-sdk` | 辅助开发者基于 ROCK Agent SDK 开发 Agent Benchmark 评测 |

**rock-agent**
| 技能 | 说明 |
|------|------|
| `rock-agent-debug` | 查询和排查 ROCK 沙箱中 Harbor Job 和 Bash Job 的状态与问题 |
