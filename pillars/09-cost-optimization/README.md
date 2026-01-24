# Cost Optimization

> "There is no cloud. It's just someone else's computer — and they're billing you for it."

## What is Cost Optimization?

Managing cloud spending to maximize value — not just cutting costs, but getting the most reliability per dollar.

## FinOps Principles

### Inform
- Visibility into spending
- Allocation to teams/products
- Forecasting

### Optimize
- Right-sizing
- Reserved capacity
- Spot/preemptible instances
- Waste elimination

### Operate
- Showback/chargeback
- Budgets and alerts
- Continuous optimization

## Key Concepts

### Unit Economics
```
Cost per request
Cost per user
Cost per transaction
Cost per GB stored
```

### Cloud Pricing Models

| Model | Discount | Commitment |
|-------|----------|------------|
| On-demand | 0% | None |
| Spot/Preemptible | 60-90% | Can be terminated |
| Reserved (1yr) | 30-40% | Payment commitment |
| Reserved (3yr) | 50-60% | Payment commitment |
| Savings Plans | 20-40% | Spend commitment |

### Cost Allocation
- Tag everything
- Allocate to teams/products
- Track untagged resources

## Topics

- [ ] Cloud cost visibility
- [ ] Resource tagging strategy
- [ ] Right-sizing analysis
- [ ] Reserved capacity planning
- [ ] Spot instance strategies
- [ ] Storage optimization
- [ ] Network cost reduction
- [ ] Idle resource cleanup
- [ ] Cost anomaly detection
- [ ] FinOps culture

## Optimization Strategies

### Compute
- Right-size instances (most are over-provisioned)
- Use spot for fault-tolerant workloads
- Auto-scale to demand
- Terminate unused resources
- Consider ARM instances (Graviton)

### Storage
- Lifecycle policies (S3, EBS snapshots)
- Right storage tier (hot/warm/cold)
- Delete orphaned volumes
- Compress and deduplicate

### Network
- Use VPC endpoints (avoid NAT gateway costs)
- Optimize cross-region traffic
- Cache at edge (CDN)
- Compress payloads

### Database
- Right-size instances
- Reserved capacity for stable workloads
- Use serverless for variable workloads
- Archive old data

## Cost Visibility

### Tagging Strategy
```
Required tags:
- environment (dev/staging/prod)
- team (owning team)
- service (application name)
- cost-center (billing code)
```

### Dashboards
- Daily/weekly cost trends
- Cost by team/service
- Cost anomalies
- Reserved utilization
- Savings opportunities

## Tools

| Tool | Purpose |
|------|---------|
| AWS Cost Explorer | AWS cost analysis |
| Kubecost | Kubernetes cost allocation |
| Infracost | Terraform cost estimation |
| Spot.io | Spot instance management |
| CloudHealth | Multi-cloud FinOps |
| Vantage | Cloud cost visibility |

## Anti-Patterns

- No cost visibility
- No tagging
- Reserved instances without utilization tracking
- Dev environments running 24/7
- Orphaned resources
- Storing everything forever
- Over-provisioning "just in case"

## Quick Wins

1. Delete unused resources (EIPs, EBS volumes, old snapshots)
2. Right-size obviously over-provisioned instances
3. Shut down dev/test outside business hours
4. Enable S3 lifecycle policies
5. Review and cancel unused reserved capacity

## Metrics

- Total cloud spend
- Cost per unit (request, user, transaction)
- Reserved instance utilization
- Spot instance ratio
- Waste (unused resources)
- Cost forecast accuracy

## Reading

- Cloud FinOps (O'Reilly)
- AWS Well-Architected: Cost Optimization Pillar
- FinOps Foundation resources
