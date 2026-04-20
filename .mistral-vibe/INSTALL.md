# Installing Superpowers for Mistral Vibe Code

## Prerequisites

- [Mistral Vibe Code](https://mistral.ai) installed

## Installation

### Option 1: Plugin Installation (Recommended)

Add superpowers to the `plugin` array in your `mistral-vibe.json` (global or project-level):

```json
{
  "plugin": ["superpowers@git+https://github.com/obra/superpowers.git"]
}
```

Restart Mistral Vibe Code. The plugin auto-installs and registers all skills.

### Option 2: Manual Skill Setup

Follow the official Mistral Vibe documentation for manual skill setup:

1. Create skills directory:
```bash
mkdir -p ~/.vibe/skills/
```

2. Clone or copy Superpowers skills to `~/.vibe/skills/`

3. Verify by asking: "Tell me about your superpowers"

## Usage

Use Mistral Vibe Code's native `skill` tool:

```
use skill tool to list skills
use skill tool to load superpowers/brainstorming
```

## Updating

Superpowers updates automatically when you restart Mistral Vibe Code.

To pin a specific version:

```json
{
  "plugin": ["superpowers@git+https://github.com/obra/superpowers.git#v5.0.3"]
}
```

## Troubleshooting

### Plugin not loading

1. Check logs: `mistral-vibe run --print-logs "hello" 2>&1 | grep -i superpowers`
2. Verify the plugin line in your `mistral-vibe.json`
3. Make sure you're running a recent version of Mistral Vibe Code

### Skills not found

1. Use `skill` tool to list what's discovered
2. Check that the plugin is loading (see above)

### Tool mapping

When skills reference Claude Code tools:
- `TodoWrite` → `todowrite`
- `Task` with subagents → `@mention` syntax
- `Skill` tool → Mistral Vibe Code's native `skill` tool
- File operations → your native tools

## Getting Help

- Report issues: https://github.com/obra/superpowers/issues
- Full documentation: https://github.com/obra/superpowers/blob/main/docs/README.mistral-vibe.md
