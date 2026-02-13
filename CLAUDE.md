# SRE Framework — Project Context

## Purpose

Training material and practical clarification of what SRE is — outside any strict definitions made by Google or any other company. This is opinionated, experience-driven, and grounded in 30+ years of operational reality.

## Guiding Philosophy

The foundational SRE philosophy for this project is documented in `manifesto/`. All content created in this project should align with these principles:

- **SRE is a role, not a team.** It's a specialization within Ops, not a separate department.
- **The concentric model applies.** SysAdmin → Cloud Engineer → Platform Engineer → SRE. Each layer includes the one before it.
- **Standby is the differentiator.** If you're not on standby, you're not doing SRE.
- **SRE = Ops + Software Engineering.** Automate operational work using engineering practices.
- **Devs make crappy SREs, and SREs make crappy devs, but together they go to greatness.**

## Structure

```
SRE/
├── manifesto/          # Foundational SRE philosophy and definitions
├── pillars/            # 10 core SRE domains (reliability, scalability, etc.)
├── patterns/           # Reusable architecture patterns with code examples
├── runbooks/           # Operational procedures (trigger → steps → verify → rollback)
├── tools/              # Tool-specific guides
└── README.md           # Project overview and entry point
```

## Content Conventions

- **Practical over theoretical.** Real-world implementation, not academic definitions.
- **Opinionated.** This is based on lived experience. State positions clearly.
- **Training-oriented.** Content should be usable for onboarding SREs and educating adjacent teams.
- **Tool-agnostic where possible.** Principles first, specific tools as examples.
- **Use the manifesto as the lens.** When in doubt about "what is SRE", refer to `manifesto/`.

## Git Workflow

**NEVER push directly to main. ALWAYS use pull requests.**

1. Create feature branch: `git checkout -b feature/description`
2. Make changes and commit
3. Push branch: `git push -u origin feature/description`
4. Create PR: `gh pr create --title "..." --body "..."`

## Working With This Project

- Read `manifesto/` first to understand the philosophical foundation
- Each pillar in `pillars/` is self-contained with its own README
- Patterns, runbooks, and tools are cross-referenced from pillars
- Content is Markdown-native — no build tooling required
- The diagram in `manifesto/concentric-model.png` is the canonical visual reference for discipline relationships
