# Facia v1 to v2 Migration

Facia v2 removes the old broad surface taxonomy and replaces it with active-use routing.

## Removed as protocol surfaces

```text
progress
action
review
control
constraint
acceptance
```

These may still appear as rendered language, but they are not Facia primitives.

## New surfaces

```text
coordinate
implement
verify
```

## Old model

```text
Surface = relation over conditions
```

## New model

```text
Condition = reference to Corus requirement status
Route     = rule that maps active condition to use
Surface   = grouped active conditions for one use
```

## Completion

Facia v2 does not surface every condition.

```text
satisfied + no downstream use = complete / no surface
```

Complete state belongs to Corus.

## Keeper

```text
Facia v1 grouped status into surfaces.
Facia v2 routes active state into use.
```
