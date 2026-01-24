# Observability

> "You can't fix what you can't see."

## What is Observability?

The ability to understand a system's internal state by examining its external outputs — without deploying new code.

## Three Pillars

### 1. Metrics
Numeric measurements over time:
- **Counters** — Cumulative values (requests_total)
- **Gauges** — Current values (temperature, queue_size)
- **Histograms** — Distribution of values (latency_bucket)
- **Summaries** — Quantiles (p50, p95, p99)

### 2. Logs
Discrete events with context:
- Structured (JSON) > Unstructured
- Include: timestamp, level, service, trace_id, message, context
- Sampling for high-volume services

### 3. Traces
Request flow across services:
- Trace = collection of spans
- Span = single operation with timing
- Propagate context (trace_id, span_id) across services

## Key Concepts

### RED Method (Request-driven)
- **Rate** — Requests per second
- **Errors** — Failed requests per second
- **Duration** — Latency distribution

### USE Method (Resource-driven)
- **Utilization** — % time resource is busy
- **Saturation** — Work queued waiting
- **Errors** — Error count

### Four Golden Signals
1. Latency
2. Traffic
3. Errors
4. Saturation

## Topics

- [ ] Metric naming conventions
- [ ] Cardinality management
- [ ] Log aggregation pipelines
- [ ] Distributed tracing implementation
- [ ] Correlation (metrics ↔ logs ↔ traces)
- [ ] Alerting strategies
- [ ] Dashboard design
- [ ] Runbook integration
- [ ] Cost of observability
- [ ] Sampling strategies

## Alerting

### Good Alerts
- Actionable — Someone needs to do something
- Urgent — It can't wait
- Symptom-based — Users are affected
- Documented — Runbook linked

### Bad Alerts
- Noisy — Fires too often, gets ignored
- Cause-based — CPU high but no user impact
- Ambiguous — What should I do?

### Alert Hierarchy
```
Page (wake someone up)
  → Ticket (fix during business hours)
    → Log (investigate when time permits)
```

## Tools

| Category | Tools |
|----------|-------|
| Metrics | Prometheus, Datadog, CloudWatch |
| Logs | ELK, Loki, Splunk |
| Traces | Jaeger, Tempo, Zipkin, X-Ray |
| Visualization | Grafana, Kibana |
| Alerting | Alertmanager, PagerDuty, Opsgenie |

## Anti-Patterns

- Alert fatigue (too many alerts)
- Vanity metrics (dashboards no one uses)
- High cardinality labels
- Missing context in logs
- No correlation between signals

## Reading

- Google SRE Book: Chapters 6, 10 (Monitoring, Alerting)
- Distributed Systems Observability (O'Reilly)
