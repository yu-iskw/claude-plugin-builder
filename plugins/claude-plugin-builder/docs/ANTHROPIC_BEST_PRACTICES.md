# Anthropic Best Practices for Claude Code Plugins

Core principles and guidelines for building effective Claude Code extensions, based on Anthropic's "Building Effective Agents" framework.

## Core Principles

1. **Start Simple**: Always choose the simplest solution that meets requirements. Only increase complexity when clearly justified.
2. **Context Efficiency**: Minimize token usage through progressive disclosure and targeted references.
3. **Eval-Driven Development**: Build evaluations before implementation. Use 20-50 test cases to define capabilities.

## Quick Reference

### For Agents (Orchestration Focus)

- **Complexity Decision Framework**: Use scoring (0-10) to match tasks to component types
- **Context Management**: Layer context (Role → Task → Details), link don't inline
- **Evaluation Strategy**: Plan 20-50 test cases before implementation

### For Skills (Implementation Focus)

Skills should reference the detailed guides below when implementing components.

## Detailed References

For comprehensive guidance, see:

- **Complexity Decision Framework**: `../skills/implement-claude-extensions/references/decision-framework.md`
  - Scoring guide (0-10) for component selection
  - Decision tree: Simple Skill → Workflow Skill → Sub-Agent → Agent Team
  - Trade-offs matrix and anti-patterns

- **Context Management**: `../skills/implement-claude-extensions/references/context-management.md`
  - Context layering patterns (Role → Task → Details)
  - Progressive disclosure strategies
  - Token optimization guidelines
  - Context sizing for different component types

- **Evaluation Strategy**: `../skills/implement-claude-extensions/references/evaluation-strategy.md`
  - Eval-driven development workflow
  - Building effective eval suites (20-50 test cases)
  - Measurement metrics and integration patterns

## Usage Guidelines

### Agents Should

- Reference this document for high-level principles
- Delegate detailed implementation guidance to skills
- Focus on orchestration, not deep technical details

### Skills Should

- Reference this document for core principles
- Link to detailed references when specific guidance is needed
- Avoid duplicating content from detailed references

## Reference Strategy

This document serves as a lightweight hub to minimize token consumption:

- **Agents**: Read this summary only
- **Skills**: Read this summary + specific detailed references as needed
- **Detailed References**: Read only when implementing specific patterns

This layered approach reduces redundant context loading while maintaining access to comprehensive guidance when required.
