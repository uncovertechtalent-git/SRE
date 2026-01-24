# Incident Management

> "It's not about preventing all failures. It's about recovering fast."

## What is Incident Management?

The structured approach to identifying, responding to, resolving, and learning from service disruptions.

## Incident Lifecycle

```
Detection → Triage → Response → Resolution → Review → Prevention
```

## Key Concepts

### Severity Levels

| Level | Definition | Response |
|-------|------------|----------|
| SEV1 | Critical — Major customer impact, revenue loss | All hands, war room |
| SEV2 | High — Significant degradation, workaround exists | On-call + escalation |
| SEV3 | Medium — Minor impact, limited scope | On-call handles |
| SEV4 | Low — Minimal impact, cosmetic | Next business day |

### Incident Roles
- **Incident Commander (IC)** — Coordinates response, makes decisions
- **Communications Lead** — Updates stakeholders, status page
- **Operations Lead** — Technical investigation and remediation
- **Scribe** — Documents timeline and actions

### MTTX Metrics
- **MTTD** — Mean Time To Detect
- **MTTA** — Mean Time To Acknowledge
- **MTTR** — Mean Time To Resolve
- **MTBF** — Mean Time Between Failures

## Topics

- [ ] On-call rotations
- [ ] Escalation paths
- [ ] War room protocols
- [ ] Status page management
- [ ] Customer communication
- [ ] Postmortem process
- [ ] Blameless culture
- [ ] Runbook development
- [ ] Incident tooling
- [ ] Chaos engineering

## On-Call

### Sustainable On-Call
- No more than 25% of time in on-call
- Maximum 2 incidents per shift
- Compensatory time off after pages
- Clear escalation when overwhelmed

### On-Call Checklist
- [ ] Laptop and connectivity
- [ ] VPN access working
- [ ] Alert routing confirmed
- [ ] Runbooks accessible
- [ ] Escalation contacts known

## Postmortems

### Structure
1. **Summary** — What happened, impact, duration
2. **Timeline** — Detailed sequence of events
3. **Root Cause** — Why it happened (5 Whys)
4. **Impact** — Users affected, revenue lost
5. **Action Items** — Specific, assigned, time-bound
6. **Lessons Learned** — What we'll do differently

### Blameless Culture
- Focus on systems, not individuals
- "What failed" not "who failed"
- Assume good intentions
- Share learnings widely

## Runbooks

### Good Runbook
- Clear trigger (when to use)
- Step-by-step actions
- Expected outcomes at each step
- Escalation criteria
- Rollback procedures
- Recently tested

## Tools

| Tool | Purpose |
|------|---------|
| PagerDuty | Alerting and on-call |
| Opsgenie | Incident management |
| Statuspage | External communication |
| Jira/Linear | Action item tracking |
| Slack/Teams | War room coordination |
| Rootly/Incident.io | Incident automation |

## Anti-Patterns

- Hero culture (one person fixes everything)
- Blame-driven postmortems
- Action items that never get done
- Runbooks that don't work
- Alert fatigue leading to ignored pages

## Reading

- Google SRE Book: Chapters 12-15 (Effective Troubleshooting, Emergency Response, Postmortem Culture)
- Incident Management for Operations (O'Reilly)
