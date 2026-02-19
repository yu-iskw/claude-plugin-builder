# Claude Plugin Builder

A specialized Claude Code plugin for managing the development lifecycle of other Claude Code extensions. It provides an orchestrator agent and a suite of skills to help design, implement, and verify plugins.

## Components

- **Agent**: `claude-plugin-manager` - Your partner in designing and managing plugin structure.
- **Skills**:
  - `implement-agent-skills`: Create and maintain valid skills.
  - `implement-agent-teams`: Configure agent collaboration.
  - `implement-hooks`: Set up event-driven behaviors.
  - `implement-plugin`: Manage manifest and packaging.
  - `plugin-verification`: Comprehensive checks for your plugin.

## Usage

Once installed, you can invoke the `claude-plugin-manager` agent to assist with your development tasks.

```bash
claude plugin install --scope project ./plugins/claude-plugin-builder
```
