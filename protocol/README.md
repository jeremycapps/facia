# Facia Protocol

Facia v1 is YAML-first.

Core files:

```text
surface.schema.yaml
condition.schema.yaml
```

Core model:

```text
conditions -> surfaces -> views
```

Condition locator:

```text
{objective}/{requirement}/{status}
```

Canonical surfaces:

```text
progress
action
review
control
constraint
acceptance
```

Keeper:

```text
Condition references Corus requirement status.
Surface groups conditions.
View renders surface.
```
