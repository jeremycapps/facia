# Facia

A small protocol for routing active Corus conditions into use surfaces.

Facia sits beneath dashboards, cards, employee views, meeting agendas, prompts, agents, and other interfaces.

Facia does not render UI.

Facia routes active evaluated Corus conditions into three uses:

```text
coordinate
implement
verify
```

## Version

Facia v2 removes the old six-surface taxonomy.

Facia no longer defines `progress`, `action`, `review`, `control`, `constraint`, or `acceptance` as protocol surfaces.

Those may appear later as rendered language, but they are not Facia primitives.

## Core model

Facia v2 has three authored concepts:

```text
Condition = reference to an objective-scoped requirement status
Route     = rule that maps an active condition to a use
Surface   = grouped active conditions for one use
```

A condition references Corus output in the form:

```text
{objective}/{requirement}/{status}
```

Example:

```text
objective.client_review/requirement.validation_present/unsatisfied
```

## Uses

```text
coordinate = align ownership, authority, sequencing, handoff, or priority
implement  = produce, change, fix, or execute something
verify     = review, validate, accept, or prove something
```

## Active routing

Facia only routes active conditions.

```text
Unsatisfied condition:
  route to coordinate, implement, or verify

Satisfied condition:
  no surface unless it creates downstream use
```

Complete state belongs to Corus. Facia surfaces only what still needs use.

## Example route

```yaml
route:
  id: route.schema_change_unsatisfied_to_implement
  match:
    domain: domain.protocol_design
    type: schema_change
    status: unsatisfied
  use: implement
  reason: The domain-bound schema change has not been completed.
```

## Example surface

```yaml
surface:
  use: implement
  conditions:
    - objective.facia_v2/requirement.surface_model_updated/unsatisfied
```

## Relation model

```text
Libera:
  Defines filesystem motion.

Domain:
  Binds Libera motion to domain meaning.

Timpos:
  Moment records observed state at an address.

Corus:
  Objective evaluates requirements into satisfied or unsatisfied state.

Facia:
  Routes active evaluated state into use.
```

## Boundaries

Facia does not define program paths.
Facia does not define domain meaning.
Facia does not record moments.
Facia does not evaluate requirement satisfaction.
Facia does not render views.
Facia does not surface complete state unless downstream use exists.

## Keeper

```text
Facia routes active evaluated state into use.

Coordinate aligns it.
Implement acts on it.
Verify trusts it.

Complete state does not surface unless downstream use exists.
```
