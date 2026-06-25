# Facia

A small protocol for grouping Corus requirement statuses into view-agnostic operational surfaces.

Facia sits beneath dashboards, cards, employee views, meeting agendas, prompts, and other interfaces.

Facia does not render UI.

Facia groups evaluated Corus requirement statuses into operational surfaces.

## Core model

Facia v1 has two authored objects:

```text
Condition = reference to an objective-scoped requirement status
Surface   = relation over conditions
```

A condition references Corus output in the form:

```text
{objective}/{requirement}/{status}
```

Example:

```text
objective.client_review/requirement.validation_present/unsatisfied
```

A surface groups conditions.

## Surfaces

Facia v1 defines six operational surfaces:

```text
Progress
Action
Review
Control
Constraint
Acceptance
```

These surfaces are view-agnostic. A dashboard, card, employee view, meeting agenda, agent prompt, or custom interface may render one or more surfaces.

## Example

```yaml
surface:
  id: surface.acceptance
  conditions:
    - objective: objective.client_review
      requirement: requirement.validation_present
      status: unsatisfied
```

The same condition can be referenced by more than one surface.

## Relation model

```text
Libera:
  Workstream relates paths.

Timpos:
  Moment records path-state at timpo.

Corus:
  Objective relates requirements.

Facia:
  Surface relates conditions.
```

## Boundaries

Facia does not define workstream paths.

Facia does not record moments.

Facia does not evaluate requirement satisfaction.

Facia does not render views.

## Keeper

```text
Corus evaluates requirement status.
Facia groups requirement status into surfaces.
Views render surfaces.
```
