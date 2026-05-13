# Audit Trail Viewer

The Audit Trail Viewer reconstructs a decision from signal to learning.

## Purpose

Every critical decision must be reconstructable. If the trace cannot be reconstructed, the decision is not governable.

## Required columns

```text
timestamp
actor
module
event
decision ID
policy status
causal reference
execution reference
feedback reference
```

## Trace sequence

```text
Signal
Graph
Atlas
Domain Pack
PolicyCore
PulseFlow
GreenCore
Execution
Feedback
Learning
```

## Example rows

```text
2026-05-13T09:14:22Z · Signal · Operational delay signal received · RECORDED
2026-05-13T09:14:24Z · Graph · Private tenant graph updated · LINKED
2026-05-13T09:14:31Z · Atlas · Causal decision candidate generated · REASONED
2026-05-13T09:14:42Z · PolicyCore · Constraint validation returned MODIFIED · MODIFIED
2026-05-13T09:15:02Z · PulseFlow · Execution workflow prepared · ORCHESTRATED
```

## UX rules

- Audit must be accessible from every critical decision card.
- Audit logs must be filterable by module, status, actor, tenant, and time range.
- Critical state changes must include before/after state.
- Human approvals must include actor, role, timestamp, and justification.
- Audit tables must be keyboard navigable.

## Core questions

The audit trail must answer:

```text
What happened?
Why did it happen?
Which causal path was activated?
Which constraints were checked?
Who approved it?
How was it executed?
What changed afterward?
```
