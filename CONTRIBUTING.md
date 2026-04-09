# Contributing to Quantum Pipes

Thank you for your interest in contributing to Quantum Pipes. This document covers contribution guidelines for both documentation and code across the ecosystem.

## Documentation Contributions

### Front Matter

Every documentation file uses YAML front matter:

```yaml
---
title: "Page Title"
description: "One-line description for search and social previews."
order: 1
tags: [relevant, tags]
related:
  - path: /other/page
    relationship: "How this page relates to the other"
---
```

### Writing Standards

- **Direct, confident voice.** Second person, active voice, present tense.
- **No em dashes.** Use commas, periods, colons, semicolons, or parentheses.
- **Code over theory.** Show working examples, not abstract explanations.
- **Verify claims.** Every technical claim must be testable against the current codebase.

### Structure

- `getting-started/` -- entry points for new users
- `architecture/` -- system design and design rationale
- `guides/` -- narrative walkthroughs
- `packages/` -- per-package deep dives
- `compliance/` -- regulatory framework mappings
- `reference/` -- API, CLI, and configuration reference
- `security/` -- security model and disclosure
- `examples/` -- runnable code examples

## Code Contributions

Each package has its own repository. See the individual repo's CONTRIBUTING.md for package-specific guidelines.

### General Standards

- **Tests required.** All contributions must include tests.
- **Type hints required.** Python: full type annotations. TypeScript: strict mode.
- **Apache-2.0 license.** All contributions are licensed under Apache-2.0.

## Reporting Issues

- **Security vulnerabilities:** See [SECURITY.md](SECURITY.md)
- **Documentation bugs:** Open an issue in this repo
- **Package bugs:** Open an issue in the relevant package repo

## Code of Conduct

Be respectful. Be constructive. Focus on the work.
