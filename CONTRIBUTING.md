# Contributing to Community Standards

Thank you for sharing your patterns with the community!

## Quick Start

1. Fork this repository
2. Add your pattern to the appropriate directory
3. Submit a Pull Request
4. Wait for community review

## Pattern Template

Use this template for new patterns:

```markdown
# Pattern Name

## Problem
What problem does this solve? Be specific.

## Context
When should someone use this pattern?
- Project size
- Team size
- Technology constraints
- Performance requirements

## Solution
Step-by-step implementation:

1. First step
2. Second step
3. etc.

### Code Example
\`\`\`javascript
// Working code example
const example = () => {
  // Implementation
};
\`\`\`

## Trade-offs
Every pattern has trade-offs. What are they?
- Performance impact?
- Complexity added?
- When NOT to use this?

## Real-World Usage
Where has this been used successfully?
- Company/Project: [Name]
- Scale: [Users/requests/data volume]
- Duration: [How long in production]
- Results: [Measurable outcomes]

## See Also
- Related patterns in this repo
- External resources
```

## Review Criteria

Patterns are reviewed for:
- ✅ **Clarity** - Easy to understand and implement
- ✅ **Completeness** - Includes problem, solution, trade-offs
- ✅ **Practicality** - Has been used in production
- ✅ **Specificity** - Specific enough to be actionable
- ✅ **Generality** - General enough for others to use

## What Gets Accepted?

**Good submissions:**
- Solve real production problems
- Include working code examples
- Document trade-offs honestly
- Proven in multiple contexts
- Well-documented with context

**Rejected submissions:**
- Theoretical/untested ideas
- Company-specific implementations
- Universal principles (belong in Open Standards)
- Incomplete documentation
- No real-world validation

## Categories

### patterns/
Recurring solutions to common problems:
- `agent-coordination-*.md`
- `error-handling-*.md`
- `state-management-*.md`
- `performance-*.md`

### examples/
Complete working implementations:
- Create a directory: `examples/pattern-name/`
- Include: README.md, code files, tests
- Document: setup, usage, expected results

### workflows/
Custom workflow patterns:
- `custom-workflow-*.md`
- Include workflow definition
- Document agent sequence
- Show expected outcomes

### integrations/
Integration with tools/services:
- `integration-[tool-name].md`
- Setup instructions
- Configuration examples
- Common pitfalls

## Review Process

1. **Submit PR** - Fill out PR template
2. **Community Review** (3-7 days) - Community members comment
3. **Curator Review** (HappyHippo.ai) - Final approval
4. **Merge** - Pattern added to repo
5. **Credit** - Added to CONTRIBUTORS.md

## Promotion to Open Standards

Exceptional patterns may be promoted to Open Standards if they:
- Apply universally (any tech stack)
- Solve fundamental problems
- Have widespread adoption
- Align with core principles

## Questions?

- Open an issue
- Email: info@happyhippo.ai
- GitHub Discussions

Thank you for contributing! 🎉
