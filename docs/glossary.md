# Glossary

## Condition

A reference to one Corus requirement status inside one objective.

```text
objective + requirement + status
```

Example:

```yaml
objective: objective.client_review
requirement: requirement.validation_present
status: unsatisfied
```

## Surface

A view-agnostic operational grouping of conditions.

Facia v1 defines six surfaces:

```text
Progress
Action
Review
Control
Constraint
Acceptance
```

## View

A downstream rendering of one or more surfaces.

Examples:

```text
dashboard
card
meeting agenda
employee view
agent prompt
client portal
```

Views are outside Facia v1.
