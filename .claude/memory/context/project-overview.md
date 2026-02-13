---
id: mem_20260124_sre001
created: 2026-01-24T18:30:00Z
updated: 2026-02-13T11:00:00Z
source: conversation
confidence: 0.95
tags: [project, sre, framework, documentation, training]
related: [mem_20260213_sre002]
---

# SRE Framework Project Overview

## Content

Training material and practical SRE definition — opinionated, experience-driven, grounded in 30+ years of operational reality. Not bound to Google's or any other company's specific SRE definition.

### Structure
```
SRE/
├── manifesto/              # Foundational SRE philosophy (concentric model, standby, ops identity)
├── pillars/
│   ├── 01-reliability/      # SLIs, SLOs, Error Budgets
│   ├── 02-scalability/      # Horizontal/Vertical, Capacity
│   ├── 03-observability/    # Metrics, Logs, Traces
│   ├── 04-incident-management/
│   ├── 05-infrastructure-as-code/
│   ├── 06-cicd-deployment/
│   ├── 07-performance/
│   ├── 08-security/
│   ├── 09-cost-optimization/
│   └── 10-toil-reduction/
├── patterns/               # Reusable architecture patterns
├── runbooks/               # Operational procedures
└── tools/                  # Tool-specific guides
```

### GitHub
https://github.com/uncovertechtalent/SRE

### Purpose
Training material + clarification of what SRE is practically. Content should be usable for onboarding SREs and educating adjacent teams.

## Context

Project created 2026-01-24. Manifesto and philosophy layer added 2026-02-13 from Stefan's direct input on the concentric operations model, standby-first definition, and practical SRE identity.
