# Runbooks

Operational procedures for common scenarios.

## Structure

Each runbook includes:
- **Trigger** — When to use this runbook
- **Prerequisites** — Access, tools needed
- **Steps** — Detailed procedure
- **Verification** — How to confirm success
- **Rollback** — How to undo if needed
- **Escalation** — When and who to contact

## Planned Runbooks

### Incidents
- [ ] Service outage response
- [ ] Database failover
- [ ] Rollback deployment
- [ ] Certificate expiry

### Operations
- [ ] Scaling a service
- [ ] Database maintenance
- [ ] Log rotation
- [ ] Backup verification

### Security
- [ ] Credential rotation
- [ ] Security incident response
- [ ] Access revocation

## Template

```markdown
# [Runbook Title]

## Trigger
When to use this runbook.

## Prerequisites
- [ ] Access to X
- [ ] Tool Y installed

## Steps
1. First step
   ```bash
   command here
   ```
   Expected output: ...

2. Second step
   ...

## Verification
How to confirm the issue is resolved.

## Rollback
How to undo changes if needed.

## Escalation
- First: @on-call
- Then: @team-lead
- Finally: @incident-commander
```
