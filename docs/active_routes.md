# Facia Active Routes

Facia routes only active evaluated state.

A condition is active when it still requires one of three uses:

```text
coordinate
implement
verify
```

A satisfied condition with no downstream use is complete and should not surface.

## Route model

```yaml
route:
  id: string

  match:
    domain: string
    type: string
    status: satisfied | unsatisfied
    downstream: object | none

  use: coordinate | implement | verify

  reason: string
```

## Uses

```text
coordinate = align ownership, authority, sequencing, handoff, or priority
implement  = produce, change, fix, or execute something
verify     = review, validate, accept, or prove something
```

## Completion rule

```yaml
complete_when:
  status: satisfied
  downstream: none
```

`complete` is not a Facia surface.

Complete state belongs to Corus. Facia surfaces only active state.

## Default pattern

```text
Unsatisfied + missing work        -> implement
Unsatisfied + missing alignment   -> coordinate
Unsatisfied + missing authority   -> coordinate
Unsatisfied + missing proof       -> verify
Unsatisfied + missing acceptance  -> verify

Satisfied + needs proof           -> verify
Satisfied + changes routing       -> coordinate
Satisfied + no downstream use     -> complete / no surface
```

## Keeper

```text
Facia routes active conditions only.
Complete state does not surface unless downstream use exists.
```
