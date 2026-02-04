# EquilateralAgents Community Standards

**Community-contributed development patterns and practices.**

Curated by HappyHippo.ai, contributed by the community.

> **51 standards | 661 rules | 280+ anti-patterns**

## What Are Community Standards?

This repository contains **battle-tested patterns** from developers using EquilateralAgents in production. These aren't universal principles (those live in [Open Core](https://github.com/Equilateral-AI/equilateral-agents-open-core)) - they're proven practices that work in specific contexts.

## Structure

```
community-standards/
├── TEMPLATE.yaml       # Copy this to start a new pattern
├── CONTRIBUTING.md     # Submission guidelines
└── patterns/           # All community standards (*.yaml)
```

## How to Use

### Add to Your Project

**Option 1: Git Submodule (Recommended)**
```bash
cd your-project
git submodule add https://github.com/Equilateral-AI/EquilateralAgents-Community-Standards.git .standards-community
```

**Option 2: Clone Separately**
```bash
git clone https://github.com/Equilateral-AI/EquilateralAgents-Community-Standards.git
```

**Option 3: Via Project/Object**
```bash
npm install -g @equilateral_ai/project-object
project-object init
```

### Reference in Your AI Assistant

Add to `.cursorrules` or `CLAUDE.md`:
```markdown
# Community Standards: ./.standards-community/

Check community patterns before implementing:
1. Search .standards-community/patterns/ for similar problems
2. Follow established conventions where applicable
```

## YAML Schema

Every standard follows this schema. See [TEMPLATE.yaml](TEMPLATE.yaml) for a copyable starting point.

### Required Fields

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier, kebab-case, must match filename |
| `category` | string | Always `patterns` for this repo |
| `priority` | integer | Injection priority: `10` = critical, `20` = important, `30` = advisory |
| `updated` | date | Last modified date in ISO format (YYYY-MM-DD) |
| `rules` | array | Actionable rules (at least one required) |
| `anti_patterns` | array | What NOT to do (at least one required) |

### Optional Fields

| Field | Type | Description |
|-------|------|-------------|
| `title` | string | Human-readable name |
| `description` | string | 1-3 sentence summary of what this pattern solves |
| `examples` | object | Named code examples (key: description, value: code block) |
| `cost_impact` | object | `bad_pattern` and `good_pattern` cost/perf descriptions |
| `context` | string | Background for humans - problem, when to use, trade-offs (not injected to agents) |
| `related` | array | IDs of related standards in this repo |
| `tags` | array | Filtering tags (e.g. `security`, `performance`, `agent`) |
| `source` | string | Origin attribution (e.g. `community`, `open-core`, `claude-flow`) |

### Rule Actions

| Action | Meaning | Injection |
|--------|---------|-----------|
| `ALWAYS` | Mandatory, no exceptions | `[REQUIRE]` |
| `NEVER` | Prohibited, no exceptions | `[AVOID]` |
| `USE` | Recommended approach/tool/pattern | `[REQUIRE]` |
| `PREFER` | Favored over alternatives, exceptions allowed | `[PREFER]` |
| `AVOID` | Discouraged but not prohibited | `[AVOID]` |

### Rule Structure

```yaml
rules:
  - action: ALWAYS
    rule: "Do this specific thing"
  - action: NEVER
    rule: "Never do this"
    applies_to:              # Optional: limit to specific file patterns
      - "src/**/*.js"
      - "**/*.ts"
```

## Contributing

Found a pattern that works? Share it with the community!

1. **Fork this repo**
2. **Copy the template:**
   ```bash
   cp TEMPLATE.yaml patterns/your-pattern-id.yaml
   ```
3. **Edit your pattern** - fill in rules, anti-patterns, examples
4. **Submit PR** with title: "Pattern: [Your Pattern Name]"

See [CONTRIBUTING.md](CONTRIBUTING.md) for full guidelines.

### Good Candidates

- Solved a real production problem
- Used successfully in multiple projects
- Specific enough to be actionable
- Follows YAML schema exactly

### Not Good Candidates

- Markdown format (use YAML)
- Theoretical/untested approaches
- Company-specific implementations
- Universal principles (submit to Open Core instead)

### Review Process

- Community reviews within 7 days
- Curator (HappyHippo.ai) approves/merges
- If pattern becomes universal, promoted to Open Core
- Contributors credited in CONTRIBUTORS.md

## Three-Tier Standards System

**Where does your pattern belong?**

1. **Open Core** (`.standards/`)
   - Universal principles
   - Technology-agnostic
   - Apply to ALL projects
   - Example: "No mocks in production code"

2. **Community Standards** (`.standards-community/` - THIS REPO)
   - Proven patterns
   - Context-specific
   - Apply to MANY projects
   - Example: "Agent retry with exponential backoff"

3. **Local Standards** (`.standards-local/` - your repo)
   - Team-specific
   - Company conventions
   - Apply to YOUR project
   - Example: "Use snake_case for database fields"

## Current Standards

51 community standards across these domains:

- **Agent Governance** - enforcement gates, adversarial defense, trust scoring, audit trails, memory governance, authority hierarchy, capability permissions, loop/budget control, uncertainty management
- **Security** - OWASP API, web application security, container security, secrets management, vulnerability scanning, OAuth flows, dependency management, GDPR compliance
- **Backend** - REST API design, architecture patterns, clean code, error handling, caching, structured logging, message queues, microservices resilience
- **Frontend** - React components, state management, accessibility, i18n, web performance
- **DevOps** - CI/CD pipelines, deployment safety, Docker optimization, infrastructure-as-code, git workflows, SLO observability, monorepo patterns
- **Testing** - TDD methodology, E2E/integration testing
- **Data** - database design, data validation
- **Documentation** - ADR patterns
- **Languages** - TypeScript patterns, Python patterns, GraphQL APIs

## License

MIT License - see [LICENSE](LICENSE)

Patterns remain property of original contributors. By submitting, you grant HappyHippo.ai permission to curate and distribute under MIT license.

## Links

- **Open Core Standards:** [equilateral-agents-open-core](https://github.com/Equilateral-AI/equilateral-agents-open-core)
- **Project/Object (CLI):** [project-object](https://github.com/Equilateral-AI/project-object)
- **MindMeld (Pro):** [mindmeld.dev](https://mindmeld.dev)
- **Equilateral AI:** [equilateral.ai](https://equilateral.ai)
- **Submit Patterns:** Open a PR
- **Questions:** info@happyhippo.ai

---

**Built by the community, curated by [HappyHippo.ai](https://happyhippo.ai)**
