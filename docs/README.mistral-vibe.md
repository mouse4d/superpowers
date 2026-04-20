# Superpowers for Mistral Vibe Code

## Overview

Superpowers integrates seamlessly with Mistral Vibe Code, providing a structured workflow for software development. This guide covers setup, usage, and best practices.

## Installation

Follow the instructions in [.mistral-vibe/INSTALL.md](../.mistral-vibe/INSTALL.md).

## Features

- **Skills**: Access all Superpowers skills (TDD, debugging, collaboration) directly in Mistral Vibe Code.
- **Tool Mapping**: Native Mistral Vibe Code tools are automatically mapped to Superpowers workflows.
- **Subagent Support**: Dispatch subagents for parallel tasks using Mistral Vibe Code's `@mention` syntax.

## Usage

### Loading Skills

Use the `skill` tool to load and activate skills:

```
use skill tool to load superpowers/brainstorming
```

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
