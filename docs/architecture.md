# Architecture

Facia is the surface layer beneath views.

Facia receives Corus requirement status and groups it into operational surfaces.

## Stack position

```text
Libera defines paths.
Timpos records path-state moments.
Corus evaluates requirement status inside objectives.
Facia groups requirement status into surfaces.
Views render surfaces.
```

## Core relation

```text
Surface relates conditions.
```

A condition references one objective-scoped requirement status:

```yaml
objective: objective.client_review
requirement: requirement.validation_present
status: unsatisfied
```

A surface groups those conditions:

```yaml
surface:
  id: surface.acceptance
  conditions:
    - objective: objective.client_review
      requirement: requirement.validation_present
      status: unsatisfied
```

## Boundary

Facia does not evaluate whether a requirement is satisfied.

Facia does not decide whether an objective is complete.

Facia does not render UI.

Facia only groups existing Corus requirement status into surfaces.
