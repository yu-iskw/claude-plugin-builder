# Agent Coordination

This project uses a layered agent architecture to orchestrate plugin development.

## Primary Agent

### Claude Plugin Manager

- **File**: [plugins/claude-plugin-builder/agents/claude-plugin-manager.md](plugins/claude-plugin-builder/agents/claude-plugin-manager.md)
- **Role**: Orchestrator of the plugin development lifecycle.
- **Usage**: Invoke for high-level tasks such as designing a new plugin, identifying required components, or coordinating a complex multi-step implementation.

## Delegation Patterns

The primary agent should **delegate** implementation details to specialized skills rather than performing direct file edits for component logic.

- **Complexity Assessment**: Handled by `implement-claude-extensions`.
- **Skill Implementation**: Handled by `implement-agent-skills`.
- **Sub-Agent Implementation**: Handled by `implement-sub-agents`.
- **Team Setup**: Handled by `implement-agent-teams`.
- **Hook Configuration**: Handled by `implement-hooks`.
- **Packaging**: Handled by `implement-plugin`.
- **Verification**: Handled by `plugin-verification`.

## Operator Guidance

- **Plan Mode**: Use `Plan mode` for architectural discussions, component selection, and defining test strategies.
- **Agent Mode**: Use `Agent mode` for incremental implementation, running tests, and executing the defined plan.
- **Workflow**: Always start with a `create_plan` call for complex tasks to ensure alignment before execution.
