# Superpowers for Mistral Vibe Code

## Overview

Superpowers integrates seamlessly with Mistral Vibe Code, providing a structured workflow for software development. This guide covers setup, usage, and best practices.

## Installation

Follow the instructions in [.mistral-vibe/INSTALL.md](../.mistral-vibe/INSTALL.md).

## Features

- **Skills**: Access all Superpowers skills (TDD, debugging, collaboration) directly in Mistral Vibe Code.
- **Tool Mapping**: Native Mistral Vibe Code tools are automatically mapped to Superpowers workflows.
- **Subagent Support**: Dispatch subagents for parallel tasks using Mistral Vibe Code's `@mention` syntax.
- **Agent Support**: Full support for Mistral Vibe's agent system including custom agents and AGENTS.md.

## Usage

### Agent Selection

Superpowers supports Mistral Vibe's agent system. Select agents using:

```bash
vibe --agent plan
vibe --agent auto-approve
```

Or use `Shift+Tab` in Interactive mode.

### Built-in Agents

- `default`: Requires approval for tool executions
- `plan`: Read-only agent for exploration and planning (auto-approve)
- `accept-edits`: Auto-approves file edits only
- `auto-approve`: Auto-approves all tool executions

### Custom Agents

Create custom agent profiles in `~/.vibe/agents/` by creating a `.toml` file:

```toml
# ~/.vibe/agents/custom.toml
display_name = "Custom Agent"
description = "My custom agent description."
safety = "neutral"  # Options: "safe" | "neutral" | "destructive" | "yolo"
auto_approve = true
enabled_tools = ["read_file", "grep"]
```

### Loading Skills

Use the `skill` tool to load and activate skills:

```
use skill tool to load superpowers/brainstorming
```

### AGENTS.md Support

Superpowers supports Mistral Vibe's AGENTS.md feature. Place an AGENTS.md file in your workspace root to provide agent-specific instructions and constraints.

See [AGENTS.md.example](../../AGENTS.md.example) for a complete example.

Key features:
- Agent-specific instructions and constraints
- Safety guidelines and requirements
- Project-specific contribution rules
- Tool usage restrictions

### Tool Equivalents

| Superpowers Tool | Mistral Vibe Code Equivalent |
|------------------|-----------------------------|
| `TodoWrite` | `todowrite` |
| `Task` | `@mention` syntax |
| `Skill` | `skill` tool |
| File operations | Native tools (`read_file`, `write_file`, etc.) |

### Example Workflow

1. **Brainstorming**:
   ```
   use skill tool to load superpowers/brainstorming
   ```

2. **Writing Plans**:
   ```
   use skill tool to load superpowers/writing-plans
   ```

3. **Executing Plans**:
   ```
   use skill tool to load superpowers/executing-plans
   ```

## Troubleshooting

### Skills Not Loading

1. Verify the plugin is listed in `mistral-vibe.json`.
2. Restart Mistral Vibe Code.
3. Check logs for errors:
   ```bash
   mistral-vibe run --print-logs "hello" 2>&1 | grep -i superpowers
   ```

### Subagent Issues

Ensure Mistral Vibe Code supports subagents. If not, use `executing-plans` instead of `subagent-driven-development`.

## Support

- **Issues**: [GitHub Issues](https://github.com/obra/superpowers/issues)
- **Documentation**: [Superpowers Docs](https://github.com/obra/superpowers/blob/main/docs/)
