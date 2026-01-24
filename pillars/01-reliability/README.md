# Reliability

> "Reliability is the most important feature."

## What is Reliability?

The ability of a system to perform its intended function under stated conditions for a specified period of time.

## Key Concepts

### Service Level Indicators (SLIs)
Quantitative measures of service behavior:
- **Availability** — % of successful requests
- **Latency** — Response time distribution (p50, p95, p99)
- **Throughput** — Requests per second
- **Error rate** — % of failed requests
- **Freshness** — Data staleness

### Service Level Objectives (SLOs)
Target values for SLIs:
```
Availability SLO: 99.9% of requests successful over 30 days
Latency SLO: p99 < 200ms over 30 days
```

### Service Level Agreements (SLAs)
Contractual commitments with consequences:
- SLA = SLO + Business consequences (refunds, penalties)
- SLAs should be less aggressive than internal SLOs

### Error Budgets
The inverse of reliability — how much failure is allowed:
```
99.9% SLO = 0.1% error budget = 43.2 minutes/month downtime allowed
99.99% SLO = 0.01% error budget = 4.32 minutes/month downtime allowed
```

## Topics

- [ ] Defining meaningful SLIs
- [ ] Setting realistic SLOs
- [ ] Error budget policies
- [ ] Reliability vs. velocity tradeoffs
- [ ] Cascading failures
- [ ] Redundancy and replication
- [ ] Graceful degradation
- [ ] Circuit breakers
- [ ] Retry strategies with backoff
- [ ] Timeouts and deadlines

## Patterns

- N+1 redundancy
- Active-passive failover
- Active-active clustering
- Geographic distribution
- Bulkhead isolation

## Anti-Patterns

- Assuming the network is reliable
- Single points of failure
- Cascading timeouts
- Retry storms
- Unbounded queues

## Tools

| Tool | Purpose |
|------|---------|
| Prometheus | SLI measurement |
| Grafana | SLO dashboards |
| Sloth | SLO generator for Prometheus |
| OpenSLO | Vendor-neutral SLO specification |

## Reading

- Google SRE Book: Chapters 3-4 (Embracing Risk, Service Level Objectives)
- The Site Reliability Workbook: Chapter 2 (Implementing SLOs)
