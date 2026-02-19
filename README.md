# Claude Plugin Builder

A monorepo for building, managing, and verifying Claude Code plugins. This repository contains the `claude-plugin-builder` plugin, which provides specialized agents and skills to orchestrate the full extension development lifecycle.

## Key Features

- **Standard Plugin Layout**: Follows best practices for Skills, Agents, Hooks, MCP, and LSP.
- **Extension Orchestrator**: The `claude-plugin-builder` plugin helps you design, implement, and verify new plugins.
- **Shared CI/CD**: Unified quality checks via `trunk` and GitHub Actions.
- **Integration Tests**: Automated smoke tests that validate manifest schemas and component discovery across all plugins.

## Repository Layout

```text
.
├── plugins/                     # Container for all plugins
│   └── claude-plugin-builder/   # Specialized plugin for extension development
│       ├── .claude-plugin/      # Plugin metadata (plugin.json)
│       ├── agents/              # Custom agent definitions
│       ├── skills/              # Model-invoked skills (SKILL.md)
│       ├── hooks/               # Event hook configurations
│       └── docs/                # Plugin-specific documentation
├── integration_tests/           # Shared testing harness
│   ├── run.sh                   # Test orchestrator (scans plugins/)
│   ├── validate-manifest.sh     # Manifest JSON schema validator
│   └── ...
├── .github/workflows/           # GitHub Actions (Lint, Integration Tests)
├── Makefile                     # Task runner
└── README.md
```

## Quickstart

1. **Install the builder plugin** to your local Claude Code environment:

   ```bash
   claude plugin install --scope project ./plugins/claude-plugin-builder
   ```

2. **Use the agent** to start building a new plugin:
   Ask Claude: "Use the claude-plugin-manager agent to design a new plugin for [your idea]"
3. **Run local checks**:

   ```bash
   make lint
   make test-integration-docker
   ```

## Development

### Adding a New Plugin

Create a new directory in `plugins/` following the [Standard Plugin Layout](https://code.claude.com/docs/en/plugins-reference#standard-plugin-layout):

- `plugins/<name>/.claude-plugin/plugin.json`: Required manifest.
- `plugins/<name>/skills/`: Agent Skills folder.
- `plugins/<name>/agents/`: Subagent markdown files.
- `plugins/<name>/hooks/`: Event hook configurations.
- `plugins/<name>/.mcp.json`: MCP configurations.
- `plugins/<name>/.lsp.json`: LSP configurations.

### Testing

The integration test runner (`./integration_tests/run.sh`) automatically discovers all directories in `plugins/` that contain a `.claude-plugin/plugin.json` file.

- Run all tests: `./integration_tests/run.sh`
- Verbose output: `./integration_tests/run.sh --verbose`
- Skip loading tests (if Claude CLI is not installed): `./integration_tests/run.sh --skip-loading`

## CI/CD

- **Trunk Check**: Runs linters and static analysis on every PR.
- **Integration Tests**: Automatically validates every plugin in the `plugins/` directory.

## License

Apache License 2.0. See `LICENSE`.
