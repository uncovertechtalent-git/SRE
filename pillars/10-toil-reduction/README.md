# Toil Reduction

> "If a human is doing something a computer could do, that's a bug."

## What is Toil?

Work that is:
- **Manual** — Requires human intervention
- **Repetitive** — Done over and over
- **Automatable** — Could be done by a machine
- **Tactical** — Reactive, not strategic
- **No enduring value** — Doesn't improve the system
- **Scales linearly** — More load = more toil

## Why Eliminate Toil?

- Toil consumes engineering time
- Toil doesn't scale
- Toil leads to burnout
- Toil is error-prone
- Time spent on toil ≠ time spent on improvements

## Google's Target

> SREs should spend no more than 50% of their time on toil.

The other 50%: engineering projects that reduce future toil.

## Key Concepts

### Toil vs. Overhead
- **Toil** — Operational work that scales with load
- **Overhead** — Necessary work (meetings, planning, training)

### Automation ROI
```
Time saved = (Time per task × Frequency) − (Development time + Maintenance)
```

Worth automating if:
- High frequency
- Time-consuming
- Error-prone
- Good ROI timeline

## Topics

- [ ] Identifying toil
- [ ] Measuring toil
- [ ] Prioritizing automation
- [ ] Self-service platforms
- [ ] Runbook automation
- [ ] ChatOps
- [ ] Event-driven automation
- [ ] Policy automation
- [ ] Self-healing systems
- [ ] Toil budgets

## Common Toil Sources

| Category | Examples |
|----------|----------|
| Provisioning | Creating accounts, VMs, databases |
| Deployments | Manual deploys, rollbacks |
| Incident response | Restarting services, clearing queues |
| Access management | Granting/revoking permissions |
| Certificate management | Renewing certs |
| Capacity management | Manual scaling |
| Data management | ETL jobs, cleanup scripts |

## Automation Levels

### Level 0: Manual
Human does everything.

### Level 1: Documented
Runbook exists, human follows it.

### Level 2: Scripted
Human triggers script, monitors result.

### Level 3: Automated
System triggers automatically, human reviews.

### Level 4: Self-Healing
System detects, responds, and recovers automatically.

## Self-Service Platforms

### Internal Developer Platform (IDP)
- Developers provision their own resources
- Guardrails, not gates
- Templates and golden paths
- Automated compliance

### Examples
- Create a new service (scaffolding, CI/CD, monitoring)
- Provision a database (with backups, access controls)
- Request access (time-bound, approved automatically)

## Tools

| Tool | Purpose |
|------|---------|
| Terraform | Infrastructure automation |
| Ansible | Configuration automation |
| Backstage | Developer portal |
| Port | Internal developer platform |
| Rundeck | Runbook automation |
| StackStorm | Event-driven automation |
| Kubernetes Operators | Application automation |

## Measuring Toil

### Track
- Time spent on toil (weekly logs)
- Tickets by category
- Manual interventions count
- Repeat incidents

### Report
- Toil % of total time
- Toil trend over time
- Top toil sources
- Automation opportunities

## Anti-Patterns

- Automating rarely-done tasks
- Complex automation for simple tasks
- Automation without monitoring
- No documentation for automation
- Automation that creates new toil

## Prioritization Framework

Score each toil task:

| Factor | Weight |
|--------|--------|
| Frequency (daily = 5, yearly = 1) | 3x |
| Time per occurrence | 2x |
| Error rate when done manually | 2x |
| Impact of errors | 1x |
| Automation complexity | -1x |

Prioritize highest scores first.

## Reading

- Google SRE Book: Chapter 5 (Eliminating Toil)
- The Site Reliability Workbook: Chapter 6 (Eliminating Toil)
- Team Topologies (Platform teams)
