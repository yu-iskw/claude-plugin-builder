# Claude Plugin Builder

Monorepo for building, managing, and verifying Claude Code plugins.

## Core Commands

- **Lint**: `make lint` (Runs `trunk check --all -y`)
- **Format**: `make format` (Runs `trunk fmt --all`)
- **Integration Tests (Local)**: `./integration_tests/run.sh`
- **Integration Tests (Docker)**: `make test-integration-docker`

## Project Structure

- `plugins/`: Container for all Claude plugins.
  - `claude-plugin-builder/`: Specialized plugin for extension development.
    - `agents/`: Custom agent definitions.
    - `skills/`: Model-invoked skills (`SKILL.md`).
    - `hooks/`: Event hook configurations.
    - `docs/`: Plugin-specific documentation.
- `integration_tests/`: Shared testing harness for validating plugin manifests and loading.
- `.github/workflows/`: CI/CD pipelines for linting and integration testing.

## Coding Standards

- **Agent/Skill Design**: Follow the guidelines in [plugins/claude-plugin-builder/docs/ANTHROPIC_BEST_PRACTICES.md](plugins/claude-plugin-builder/docs/ANTHROPIC_BEST_PRACTICES.md).
- **Standard Layout**: Adhere to the [Claude Plugin Standard Layout](https://code.claude.com/docs/en/plugins-reference#standard-plugin-layout).
- **Language**: Documentation and agent instructions should be clear, deterministic, and focus on progressive disclosure.
