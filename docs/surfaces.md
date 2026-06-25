# Surfaces

Facia v1 defines six view-agnostic operational surfaces.

## Progress

Groups conditions that show whether work is moving.

## Action

Groups conditions that show what work needs to happen.

## Review

Groups conditions that show what is ready for judgment.

## Control

Groups conditions that show where steering or authority is needed.

## Constraint

Groups conditions that show what limits, requirements, or validation states govern the work.

## Acceptance

Groups conditions that show whether work can be received as done.

## Common compositions

These are documentation patterns, not protocol primitives.

```text
Owner: Progress + Control
Executor: Action + Constraint
Consumer: Review + Acceptance
Manager: Progress + Constraint + Control
Team Lead: Action + Constraint + Control
QA: Review + Constraint + Acceptance
```
