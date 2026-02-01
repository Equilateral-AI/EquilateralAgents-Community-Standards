# EquilateralAgents Community Standards

**Community-contributed development patterns and practices.**

Curated by HappyHippo.ai, contributed by the community.

## What Are Community Standards?

This repository contains **battle-tested patterns** from developers using EquilateralAgents in production. These aren't universal principles (those live in [Open Standards](https://github.com/Equilateral-AI/EquilateralAgents-Open-Standards)) - they're proven practices that work in specific contexts.

## Structure

```
community-standards/
├── TEMPLATE.yaml       # Copy this to start a new pattern
├── CONTRIBUTING.md     # Submission guidelines
├── patterns/           # Recurring solutions (*.yaml)
├── examples/           # Real-world implementations (*.yaml)
├── workflows/          # Community workflow patterns (*.yaml)
└── integrations/       # Integration patterns (*.yaml)
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

### Reference in Your AI Assistant

Add to `.cursorrules` or `CLAUDE.md`:
```markdown
# Community Standards: ./.standards-community/

Check community patterns before implementing:
1. Search .standards-community/patterns/ for similar problems
2. Review .standards-community/examples/ for implementation details
3. Follow established conventions where applicable
```

## Contributing

Found a pattern that works? Share it with the community!

### YAML Format Required

All submissions must use **YAML format** for machine parsing by AI agents.

See [CONTRIBUTING.md](CONTRIBUTING.md) for full details and the [TEMPLATE.yaml](TEMPLATE.yaml) to get started.

### Quick Start

1. **Fork this repo**
2. **Copy the template:**
   ```bash
   cp TEMPLATE.yaml patterns/your-pattern-id.yaml
   ```
3. **Edit your pattern** - fill in rules, anti-patterns, examples
4. **Submit PR** with title: "Pattern: [Your Pattern Name]"

### Good Candidates

- ✅ Solved a real production problem
- ✅ Used successfully in multiple projects
- ✅ Specific enough to be actionable
- ✅ Follows YAML schema exactly

### Not Good Candidates

- ❌ Markdown format (use YAML)
- ❌ Theoretical/untested approaches
- ❌ Company-specific implementations
- ❌ Universal principles (submit to Open Standards instead)

### Review Process

- Community reviews within 7 days
- Curator (HappyHippo.ai) approves/merges
- If pattern becomes universal → Promoted to Open Standards
- Contributors credited in CONTRIBUTORS.md

## Pattern Categories

### Patterns
Recurring solutions to common problems:
- Agent coordination patterns
- Error handling strategies
- State management approaches
- Performance optimization techniques

### Examples
Real-world implementations:
- Complete working code
- Production use cases
- Integration examples
- Testing strategies

### Workflows
Community workflow patterns:
- Custom agent workflows
- CI/CD integrations
- Deployment patterns
- Monitoring setups

### Integrations
Integration patterns with tools/services:
- Third-party service integrations
- Tool-specific patterns
- Platform adaptations
- Migration guides

## Three-Tier Standards System

**Where does your pattern belong?**

1. **Open Standards** (`.standards/`)
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

## License

MIT License - see [LICENSE](LICENSE)

Patterns remain property of original contributors. By submitting, you grant HappyHippo.ai permission to curate and distribute under MIT license.

## Contact

- **Submit Patterns:** Open a PR
- **Questions:** info@happyhippo.ai
- **Discussions:** GitHub Discussions

---

**Built by the community, curated by [HappyHippo.ai](https://happyhippo.ai)**
