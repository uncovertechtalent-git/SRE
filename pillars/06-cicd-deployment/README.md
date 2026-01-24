# CI/CD & Deployment

> "If it hurts, do it more often."

## What is CI/CD?

- **Continuous Integration** — Merge code frequently, validate automatically
- **Continuous Delivery** — Code is always deployable
- **Continuous Deployment** — Every change goes to production automatically

## Deployment Strategies

### Big Bang
- All at once
- Simple but risky
- Use only for dev/test

### Rolling Update
- Gradual replacement of instances
- Zero downtime
- Mixed versions during rollout

### Blue-Green
- Two identical environments
- Instant switchover
- Easy rollback
- 2x infrastructure cost

### Canary
- Small % of traffic to new version
- Monitor for errors
- Gradually increase if healthy
- Best for catching real-world issues

### Feature Flags
- Deploy code without enabling feature
- Enable for specific users/% of traffic
- Decouple deployment from release

## Key Concepts

### Pipeline Stages
```
Commit → Build → Test → Security Scan → Deploy Dev → Deploy Staging → Deploy Prod
```

### Artifact Management
- Build once, deploy everywhere
- Immutable artifacts (Docker images, binaries)
- Versioned and tagged
- Signed and verified

### Environment Promotion
```
Dev → Staging → Production
     (same artifact)
```

## Topics

- [ ] Pipeline design patterns
- [ ] Build optimization (caching, parallelization)
- [ ] Test strategies (unit, integration, e2e)
- [ ] Security scanning (SAST, DAST, SCA)
- [ ] Deployment automation
- [ ] Rollback strategies
- [ ] Feature flags implementation
- [ ] Database migrations
- [ ] Configuration management
- [ ] Secrets in pipelines

## Progressive Delivery

### Canary Analysis
```
Deploy canary (5% traffic)
  → Monitor metrics (errors, latency)
    → Compare to baseline
      → Pass: Increase traffic
      → Fail: Automatic rollback
```

### Metrics to Watch During Rollout
- Error rate (4xx, 5xx)
- Latency (p50, p95, p99)
- Resource usage
- Business metrics (conversions, revenue)

## Tools

| Tool | Purpose |
|------|---------|
| GitHub Actions | CI/CD pipelines |
| GitLab CI | CI/CD pipelines |
| ArgoCD | Kubernetes GitOps |
| Flux | Kubernetes GitOps |
| Spinnaker | Advanced deployment strategies |
| Flagger | Progressive delivery for Kubernetes |
| LaunchDarkly | Feature flags |
| Argo Rollouts | Canary/Blue-green for Kubernetes |

## Pipeline Best Practices

### Fast Feedback
- Fail fast (run quick tests first)
- Parallelize where possible
- Cache dependencies
- Target: < 10 minutes for CI

### Secure Pipelines
- No secrets in code
- Use OIDC for cloud auth
- Scan dependencies
- Sign artifacts
- Audit pipeline changes

## Anti-Patterns

- Long-running pipelines (> 30 min)
- Manual approval gates everywhere
- No rollback plan
- Deploying on Fridays
- Snowflake environments
- Testing in production (without feature flags)

## Reading

- Accelerate (Forsgren, Humble, Kim)
- Continuous Delivery (Humble, Farley)
- Google SRE Book: Chapter 8 (Release Engineering)
