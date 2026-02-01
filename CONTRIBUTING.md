# Contributing to Community Standards

Thank you for sharing your patterns with the community!

## Quick Start

1. Fork this repository
2. Add your pattern using the **YAML format** (see template below)
3. Submit a Pull Request
4. Wait for community review

## YAML Format Required

All new submissions must use the YAML format. This enables:
- Machine parsing by AI agents (MindMeld, Claude, Cursor)
- Automated validation
- Consistent structure across all standards

### YAML Template

Create a file named `your-pattern-id.yaml`:

```yaml
id: your-pattern-id              # Unique, kebab-case, matches filename
category: patterns               # patterns | examples | workflows | integrations
priority: 20                     # 10=critical, 20=important, 30=advisory
updated: 2026-01-28              # ISO date

# Human-readable metadata
title: Your Pattern Name
description: |
  Brief description of what this pattern solves and when to use it.

# Actionable rules (required)
rules:
  - action: ALWAYS               # ALWAYS | NEVER | USE | PREFER | AVOID
    rule: Do this specific thing
  - action: NEVER
    rule: Avoid this specific anti-pattern
  - action: USE
    rule: Recommended approach for X scenario
    applies_to:                  # Optional: file patterns where this applies
      - "src/**/*.js"

# What NOT to do (required)
anti_patterns:
  - "Specific bad pattern with code example if helpful"
  - "Another thing to avoid"

# Code examples (optional but encouraged)
examples:
  correct_implementation: |
    // Working code example
    const example = () => {
      // Implementation
    };
  wrong_implementation: |
    // What NOT to do
    const badExample = () => {
      // Anti-pattern
    };

# Background context for humans (optional, not injected to agents)
context: |
  ## Problem
  What problem does this solve? Be specific.

  ## When to Use
  - Project size considerations
  - Team size considerations
  - Technology constraints
  - Performance requirements

  ## Trade-offs
  - Performance impact?
  - Complexity added?
  - When NOT to use this?

  ## Real-World Usage
  - Project: [Name]
  - Scale: [Users/requests/data volume]
  - Duration: [How long in production]
  - Results: [Measurable outcomes]

# Cost/performance impact (optional)
cost_impact:
  bad_pattern: "$X/month or performance penalty"
  good_pattern: "$0 or performance benefit"

# Related standards (optional)
related:
  - other-pattern-id
  - another-pattern-id

# Tags for filtering (optional but encouraged)
tags:
  - agent-coordination
  - error-handling
  - performance
```

### Action Definitions

| Action | Meaning |
|--------|---------|
| `ALWAYS` | Mandatory, no exceptions |
| `NEVER` | Prohibited, no exceptions |
| `USE` | Recommended approach/tool/pattern |
| `PREFER` | Favored over alternatives, exceptions allowed |
| `AVOID` | Discouraged but not prohibited |

## Schema Reference

Full schema documentation: [equilateral-standards-yaml/SCHEMA.yaml](https://github.com/Equilateral-AI/equilateral-standards-yaml/blob/main/SCHEMA.yaml)

## Validation

Before submitting, validate your YAML:

```bash
# Basic syntax check
cat your-pattern.yaml | python -c "import sys, yaml; yaml.safe_load(sys.stdin)"

# Or use any YAML linter
npx yaml-lint your-pattern.yaml
```

**Validation rules:**
- `id` must be unique and match filename
- `rules` array must have at least one rule
- Each rule must have `action` and `rule` fields
- `anti_patterns` array must have at least one entry
- `updated` must be valid ISO date (YYYY-MM-DD)

## Review Criteria

Patterns are reviewed for:
- **Clarity** - Easy to understand and implement
- **Completeness** - Includes rules, anti-patterns, examples
- **Practicality** - Has been used in production
- **Specificity** - Specific enough to be actionable
- **Generality** - General enough for others to use

## What Gets Accepted?

**Good submissions:**
- Solve real production problems
- Include working code examples
- Document trade-offs honestly
- Proven in multiple contexts
- Follow YAML schema exactly

**Rejected submissions:**
- Markdown format (use YAML)
- Theoretical/untested ideas
- Company-specific implementations
- Universal principles (belong in Open Standards)
- Incomplete or invalid YAML

## Categories

### patterns/
Recurring solutions to common problems:
- `agent-coordination-*.yaml`
- `error-handling-*.yaml`
- `state-management-*.yaml`
- `performance-*.yaml`

### examples/
Complete working implementations:
- Create: `examples/pattern-name.yaml`
- Include code in `examples` field
- Document setup and expected results

### workflows/
Custom workflow patterns:
- `workflow-*.yaml`
- Include workflow definition in examples
- Document agent sequence

### integrations/
Integration with tools/services:
- `integration-[tool-name].yaml`
- Setup instructions in context
- Configuration in examples

## Review Process

1. **Submit PR** - YAML file in appropriate directory
2. **Automated Validation** - CI checks YAML syntax and schema
3. **Community Review** (3-7 days) - Community members comment
4. **Curator Review** (HappyHippo.ai) - Final approval
5. **Merge** - Pattern added to repo
6. **Credit** - Added to CONTRIBUTORS.md

## Promotion to Open Standards

Exceptional patterns may be promoted to Open Standards if they:
- Apply universally (any tech stack)
- Solve fundamental problems
- Have widespread adoption
- Align with core principles

## Migrating Existing Markdown

If you have an existing markdown pattern, convert it:

1. Extract actionable rules → `rules:` array
2. Extract anti-patterns → `anti_patterns:` array
3. Move code examples → `examples:` object
4. Move prose → `context:` field
5. Add required metadata (`id`, `category`, `priority`, `updated`)

## Questions?

- Open an issue
- Email: info@happyhippo.ai
- GitHub Discussions

Thank you for contributing!
