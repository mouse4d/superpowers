# Mistral Vibe Code Tool Mapping

This reference translates Superpowers tool calls to Mistral Vibe Code's native tools.

## Core Tools

| Superpowers Tool | Mistral Vibe Code Tool |
|------------------|-----------------------|
| `TodoWrite` | `todowrite` |
| `Task` (subagents) | `@mention` syntax |
| `Skill` | `skill` tool |
| `Read` | `read_file` |
| `Write` | `write_file` |
| `Edit` | `search_replace` |
| `Bash` | `bash` |
| `Grep` | `grep` |

## Subagent Support

Mistral Vibe Code supports subagents via `@mention` syntax. Use this for parallel task execution:

```
@subagent implement feature X
```

## Limitations

- **No native subagent API**: Use `@mention` for task delegation.
- **Tool names**: Mistral Vibe Code uses snake_case (e.g., `read_file` instead of `Read`).

## Example Workflow

1. **Load a skill**:
   ```
   use skill tool to load superpowers/brainstorming
   ```

2. **Read a file**:
   ```
   read_file(path="src/index.js")
   ```

3. **Write a file**:
   ```
   write_file(path="src/new.js", content="export const foo = 'bar';")
   ```

4. **Dispatch a subagent**:
   ```
   @subagent write tests for src/new.js
   ```
