# Performance

> "Premature optimization is the root of all evil. But mature optimization is the root of all good."

## What is Performance?

How efficiently a system uses resources to serve requests — measured in latency, throughput, and resource utilization.

## Key Metrics

### Latency
- **p50** — Median (half of requests faster)
- **p95** — 95th percentile (most users' experience)
- **p99** — 99th percentile (tail latency, worst experience)
- **p99.9** — Critical for high-traffic systems

> Focus on percentiles, not averages. Averages hide the pain.

### Throughput
- Requests per second (RPS)
- Transactions per second (TPS)
- Messages per second (MPS)

### Resource Utilization
- CPU usage
- Memory usage
- Disk I/O
- Network bandwidth
- Connection pool usage

## Key Concepts

### Little's Law
```
L = λ × W

L = average number of items in system
λ = average arrival rate
W = average time in system
```

### Amdahl's Law
```
Speedup = 1 / ((1 - P) + P/S)

P = proportion that can be parallelized
S = speedup of parallel portion
```
The serial portion limits total speedup.

### Latency Numbers Every Programmer Should Know
```
L1 cache reference                  0.5 ns
L2 cache reference                    7 ns
Main memory reference               100 ns
SSD random read               150,000 ns (150 µs)
HDD random read            10,000,000 ns (10 ms)
Network round trip same DC    500,000 ns (500 µs)
Network round trip US→EU   150,000,000 ns (150 ms)
```

## Topics

- [ ] Profiling techniques
- [ ] Database query optimization
- [ ] Caching strategies
- [ ] Connection pooling
- [ ] Async processing
- [ ] Compression
- [ ] CDN optimization
- [ ] Load testing
- [ ] Capacity planning
- [ ] Performance budgets

## Optimization Process

### 1. Measure
- Profile before optimizing
- Identify bottlenecks with data
- Establish baseline metrics

### 2. Analyze
- Find the critical path
- Look for O(n²) operations
- Check for unnecessary work

### 3. Optimize
- Fix the biggest bottleneck first
- One change at a time
- Verify improvement with measurement

### 4. Validate
- Load test the change
- Check for regressions
- Monitor in production

## Common Bottlenecks

| Layer | Common Issues |
|-------|---------------|
| Network | Too many round trips, no compression, no CDN |
| Application | N+1 queries, synchronous blocking, no caching |
| Database | Missing indexes, full table scans, locks |
| Infrastructure | Under-provisioned, wrong instance type |

## Caching Strategy

### Cache Hierarchy
```
Browser Cache → CDN → Application Cache → Database Cache → Database
```

### Cache Patterns
- **Cache-aside** — App manages cache
- **Read-through** — Cache manages reads
- **Write-through** — Cache manages writes
- **Write-behind** — Async write to DB

### Cache Invalidation
> "There are only two hard things in CS: cache invalidation and naming things."

- TTL-based expiration
- Event-driven invalidation
- Version-based invalidation

## Tools

| Tool | Purpose |
|------|---------|
| pprof | Go profiling |
| py-spy | Python profiling |
| async-profiler | JVM profiling |
| k6 | Load testing |
| Locust | Load testing |
| Gatling | Load testing |
| pganalyze | PostgreSQL analysis |

## Anti-Patterns

- Optimizing without measuring
- Caching without invalidation strategy
- N+1 queries
- Synchronous external calls
- Unbounded queries
- No connection pooling

## Reading

- High Performance Browser Networking (Grigorik)
- Systems Performance (Gregg)
- Google SRE Book: Chapter 21 (Handling Overload)
