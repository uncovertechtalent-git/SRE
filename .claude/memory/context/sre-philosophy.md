---
id: mem_20260213_sre002
created: 2026-02-13T11:00:00Z
updated: 2026-02-13T11:00:00Z
source: conversation
confidence: 0.98
tags: [philosophy, sre, manifesto, concentric-model, standby, ops]
related: [mem_20260124_sre001]
---

# SRE Philosophy — Stefan's Practical Definition

## Core Position

SRE is a **role**, not a team. It is a specialization within Ops — the outermost ring of the concentric operations model.

## The Concentric Model

Ops disciplines nest concentrically. Each outer layer includes everything in the layers beneath it:

```
[SRE]
  [Platform Engineers]
    [Cloud Engineers]
      [System / Network Admins]
```

- **System/Network Admins**: Core operations. Hardware, networking, OS management.
- **Cloud Engineers**: SysAdmin skills + cloud platform expertise.
- **Platform Engineers**: Cloud engineer skills + developer tooling, internal platforms.
- **SRE**: Platform engineer skills + software engineering applied to operational problems + standby.

## Adjacent Disciplines (Overlapping Circles)

- **DevOps**: Overlap between Development Engineering and Ops (specifically SRE/Platform). Cultural and process bridge.
- **FinOps**: Overlap between Finance and Ops. Cloud cost management.
- **SecOps**: Overlap between Security and Ops. Operational security.
- **DataOps**: Overlap between Data and Ops. Data pipeline reliability.

## The Standby Differentiator

The single clearest distinction of SRE: **standby rotation**. SRE carries the pager. SRE is primary on-call for production outages, with platform teams and sysadmins on secondary rotation via escalation paths.

## SRE = Ops + Software Engineering

An SRE takes operational work and applies software engineering practices to it — automation, tooling, reliability patterns. The role requires sufficient ops knowledge as foundation, plus the engineering mindset to automate and systematize.

## Team Composition

In Stefan's model:
- SRE is embedded within the Ops function, not a separate team alongside Dev
- Platform and Ops teams have their own standby schedules
- Escalation paths route to the appropriate team's standby person
- SRE is primary for production outages

## Key Quotes

- "Devs make crappy SREs, and SREs make crappy devs, but together they go to greatness."
- "SREs can have any background, as long as sufficient ops knowledge is in place, and there is a desire for standby."

## Visual Reference

The concentric model diagram is stored at `manifesto/concentric-model.png`.
