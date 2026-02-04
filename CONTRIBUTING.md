# Contributing to Community Standards

Thank you for sharing your patterns with the community!

## Quick Start

1. Fork this repository
2. Add your pattern using the **YAML format** (see template below)
3. Place your file in `patterns/`
4. Submit a Pull Request
5. Wait for community review

## YAML Format Required

All submissions must use YAML format. This enables:
- Machine parsing by AI agents (MindMeld, Claude, Cursor)
- Automated validation
- Consistent structure across all standards

### YAML Template

Create a file named `your-pattern-id.yaml` in `patterns/`:

```yaml
id: your-pattern-id              # Unique, kebab-case, matches filename
category: patterns               # Always "patterns" for this repo
priority: 20                     # 10=critical, 20=important, 30=advisory
updated: 2026-02-04              # ISO date

title: Your Pattern Name
description: |
  Brief description of what this pattern solves and when to use it.

rules:
  - action: ALWAYS               # ALWAYS | NEVER | USE | PREFER | AVOID
    rule: Do this specific thing
  - action: NEVER
    rule: Avoid this specific anti-pattern

anti_patterns:
  - "Specific bad pattern with code example if helpful"
  - "Another thing to avoid"

examples:
  correct_implementation: |
    // Working code example
  wrong_implementation: |
    // What NOT to do

context: |
  Background for humans (not injected to agents).
  Problem description, when to use, trade-offs.

related:
  - other-pattern-id

tags:
  - relevant-tag
```

## Field Reference

### Required Fields

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique kebab-case identifier, must match filename (without `.yaml`) |
| `category` | string | Always `patterns` |
| `priority` | integer | `10` = critical (injected first), `20` = important, `30` = advisory |
| `updated` | date | ISO format `YYYY-MM-DD`, set to date of last meaningful change |
| `rules` | array | At least one rule with `action` and `rule` fields |
| `anti_patterns` | array | At least one quoted string describing what to avoid |

### Optional Fields

| Field | Type | Description |
|-------|------|-------------|
| `title` | string | Human-readable name for display |
| `description` | string | 1-3 sentence summary |
| `examples` | object | Named code blocks (key = label, value = code) |
| `cost_impact` | object | `bad_pattern` and `good_pattern` strings |
| `context` | string | Background prose for humans — not injected to agents |
| `related` | array | IDs of related standards in this repo |
| `tags` | array | Filtering tags (e.g. `security`, `performance`, `agent`) |
| `source` | string | Origin attribution (e.g. `community`, `claude-flow`) |

### Rule Actions

| Action | Meaning | Agent Injection |
|--------|---------|-----------------|
| `ALWAYS` | Mandatory, no exceptions | Injected as `[REQUIRE]` |
| `NEVER` | Prohibited, no exceptions | Injected as `[AVOID]` |
| `USE` | Recommended approach/tool/pattern | Injected as `[REQUIRE]` |
| `PREFER` | Favored over alternatives, exceptions allowed | Injected as `[PREFER]` |
| `AVOID` | Discouraged but not prohibited | Injected as `[AVOID]` |

### Rule Structure

Each rule in the `rules` array has:

| Field | Required | Description |
|-------|----------|-------------|
| `action` | Yes | One of: `ALWAYS`, `NEVER`, `USE`, `PREFER`, `AVOID` |
| `rule` | Yes | The actionable directive as a quoted string |
| `applies_to` | No | Array of glob patterns limiting which files this rule applies to |

## Validation

Before submitting, validate your YAML:

```bash
# Basic syntax check
cat your-pattern.yaml | python -c "import sys, yaml; yaml.safe_load(sys.stdin)"

# Or use any YAML linter
npx yaml-lint your-pattern.yaml
```

**Validation rules:**
- `id` must be unique across all patterns and match the filename
- `rules` array must have at least one rule
- Each rule must have `action` and `rule` fields
- `anti_patterns` array must have at least one entry
- `updated` must be a valid ISO date (YYYY-MM-DD)

## Review Criteria

Patterns are reviewed for:
- **Clarity** - Easy to understand and implement
- **Completeness** - Includes rules and anti-patterns at minimum
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
- Universal principles (belong in Open Core)
- Incomplete or invalid YAML

## Review Process

1. **Submit PR** - YAML file in `patterns/` directory
2. **Automated Validation** - CI checks YAML syntax
3. **Community Review** (3-7 days) - Community members comment
4. **Curator Review** (HappyHippo.ai) - Final approval
5. **Merge** - Pattern added to repo
6. **Credit** - Added to CONTRIBUTORS.md

## Promotion to Open Core

Exceptional patterns may be promoted to [Open Core](https://github.com/Equilateral-AI/equilateral-agents-open-core) if they:
- Apply universally (any tech stack)
- Solve fundamental problems
- Have widespread adoption
- Align with core principles

## Migrating Existing Markdown

If you have an existing markdown pattern, convert it:

1. Extract actionable rules -> `rules:` array
2. Extract anti-patterns -> `anti_patterns:` array
3. Move code examples -> `examples:` object
4. Move prose -> `context:` field
5. Add required metadata (`id`, `category`, `priority`, `updated`)

## Questions?

- Open an issue
- Email: info@happyhippo.ai
- GitHub Discussions

Thank you for contributing!
