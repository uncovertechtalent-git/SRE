# Scalability

> "Scale is not a feature you can bolt on later."

## What is Scalability?

The ability of a system to handle increased load by adding resources — without architectural changes.

## Scaling Dimensions

### Vertical Scaling (Scale Up)
- Bigger machines (more CPU, RAM, disk)
- Simple but has hard limits
- Single point of failure remains

### Horizontal Scaling (Scale Out)
- More machines
- Theoretically unlimited
- Requires stateless design or distributed state

## Key Concepts

### Load Characteristics
- **Read-heavy** — Caching, read replicas, CDN
- **Write-heavy** — Sharding, write-ahead logs, eventual consistency
- **Compute-heavy** — Horizontal pods, job queues, batch processing
- **Storage-heavy** — Tiered storage, data lifecycle, compression

### Capacity Planning
```
Capacity = Current load × Growth factor × Safety margin
```
- Know your limits before you hit them
- Load test to find breaking points
- Plan for 2x headroom minimum

### Auto-Scaling
- **Reactive** — Scale based on current metrics (CPU, memory, queue depth)
- **Predictive** — Scale based on forecasted load
- **Scheduled** — Scale based on known patterns (business hours, events)

## Topics

- [ ] Stateless vs. stateful services
- [ ] Database scaling patterns
- [ ] Caching strategies
- [ ] Queue-based load leveling
- [ ] Sharding strategies
- [ ] Consistent hashing
- [ ] Read replicas
- [ ] Connection pooling
- [ ] Rate limiting
- [ ] Backpressure

## Patterns

### Stateless Services
```
Request → Load Balancer → Any Instance → Shared State (DB/Cache)
```

### Database Scaling
| Pattern | Use Case |
|---------|----------|
| Read replicas | Read-heavy workloads |
| Vertical partitioning | Split by feature domain |
| Horizontal sharding | Large datasets |
| CQRS | Separate read/write models |

### Caching Layers
```
Client → CDN → App Cache → Database Cache → Database
```

## Anti-Patterns

- Distributed monolith
- Shared mutable state
- Synchronous chains
- N+1 queries
- Unbounded growth (logs, caches, queues)

## Tools

| Tool | Purpose |
|------|---------|
| Kubernetes HPA | Horizontal Pod Autoscaler |
| KEDA | Event-driven autoscaling |
| AWS Auto Scaling | Cloud autoscaling |
| Redis | Distributed caching |
| Kafka | Message queuing |

## Metrics to Watch

- Request latency (p50, p95, p99)
- Throughput (RPS)
- Queue depth
- Resource utilization (CPU, memory, connections)
- Error rates during scale events

## Reading

- Google SRE Book: Chapter 22 (Addressing Cascading Failures)
- Designing Data-Intensive Applications: Chapters 1, 5-6
