# Security

> "Security is a process, not a product."

## What is Security in SRE?

Protecting systems, data, and users from unauthorized access, breaches, and attacks — while maintaining reliability and velocity.

## Core Principles

### Defense in Depth
Multiple layers of security controls:
```
Network → Infrastructure → Application → Data
```

### Least Privilege
- Minimum permissions necessary
- Time-bound access
- Regular access reviews

### Zero Trust
- Never trust, always verify
- Authenticate everything
- Encrypt everything

### Shift Left
- Security early in development
- Automated security testing
- Developer education

## Key Concepts

### CIA Triad
- **Confidentiality** — Only authorized access
- **Integrity** — Data is accurate and unmodified
- **Availability** — Systems accessible when needed

### Attack Surface
- External endpoints
- Internal services
- Third-party integrations
- Supply chain (dependencies)

### Threat Modeling
- What are we building?
- What can go wrong?
- What are we doing about it?
- Did we do a good job?

## Topics

- [ ] Secrets management
- [ ] Identity and access management
- [ ] Network security
- [ ] Container security
- [ ] Supply chain security
- [ ] Vulnerability management
- [ ] Security monitoring
- [ ] Incident response
- [ ] Compliance automation
- [ ] Penetration testing

## Secrets Management

### Don't
- Secrets in code
- Secrets in environment variables (visible in process list)
- Secrets in CI/CD logs
- Shared secrets

### Do
- Secrets in vault (HashiCorp Vault, AWS Secrets Manager)
- Dynamic/short-lived credentials
- Rotation automation
- Audit logging

## Container Security

### Image Security
- Minimal base images (distroless, alpine)
- No root user
- Scan for vulnerabilities
- Sign images

### Runtime Security
- Read-only filesystem
- Drop capabilities
- Resource limits
- Network policies

### Kubernetes Security
```yaml
securityContext:
  runAsNonRoot: true
  readOnlyRootFilesystem: true
  allowPrivilegeEscalation: false
  capabilities:
    drop: ["ALL"]
```

## Supply Chain Security

### SLSA Framework (Levels 1-4)
- Source integrity
- Build integrity
- Provenance
- Common requirements

### Dependency Management
- Pin versions
- Automated updates (Dependabot, Renovate)
- Vulnerability scanning
- SBOM generation

## Tools

| Tool | Purpose |
|------|---------|
| HashiCorp Vault | Secrets management |
| AWS Secrets Manager | Cloud secrets |
| Trivy | Container scanning |
| Snyk | Dependency scanning |
| Falco | Runtime security |
| OPA/Gatekeeper | Policy enforcement |
| SOPS | Encrypted secrets in Git |
| Teleport | Zero-trust access |

## Security Monitoring

### What to Monitor
- Authentication failures
- Authorization failures
- Privileged operations
- Data access patterns
- Network anomalies
- Configuration changes

### Alerting
- Failed login attempts (brute force)
- Privilege escalation
- Unusual data access
- Policy violations

## Anti-Patterns

- Security as afterthought
- Perimeter-only security
- Long-lived credentials
- Shared accounts
- No audit logging
- Security through obscurity

## Compliance

### Common Frameworks
- SOC 2
- ISO 27001
- PCI DSS
- HIPAA
- GDPR

### Automation
- Policy as code
- Continuous compliance
- Evidence collection
- Drift detection

## Reading

- Google SRE Book: Chapter 9 (Simplicity)
- Building Secure & Reliable Systems (Google)
- OWASP guidelines
