# Window Head Height Overrides

Use **Window Head Height Overrides** when one or more Windows need a head height that differs from the normal project standard.

Flow keeps these exceptions within the Global Parameter system rather than treating them as uncontrolled manual changes.

---

## Standard Head Height Parameters

The documented standard Window head-height Global Parameters are:

| Window | Standard Global Parameter |
| --- | --- |
| New | `Window Head Height` |
| Existing | `X-Window Head Height` |

An override allows selected Windows to use a separate controlled Global Parameter while the remaining Windows continue to follow the normal project value.

The Opening Register provides a **Head Height GP** column so these associations can be reviewed.

➡️ [**Opening Global Parameters**](opening-global-parameters.md)

---

## Individual Overrides

Use an individual override when one Window needs its own head-height control.

The documented workflow:

1. checks the Window's current standard association
2. repairs the standard association first if required
3. creates or finds the required override Global Parameter
4. copies the current standard value into the override
5. associates the selected Window with that override

Because the current standard value is copied first, creating the override does not itself need to move the Window.

You can then change the override value independently.

!!! tip "Create the override before changing its value"

    The override starts from the current standard head-height value.

    This separates the Window from the project-wide control without immediately changing its head height.

---

## Shared Overrides

Use a shared override when several Windows need to follow the same alternative head height.

The documented shared-override workflow uses a suffix to create a Global Parameter in the form:

```text
X-Window Head Height_<suffix>
```

For example:

```text
X-Window Head Height_Lower
```

The selected Windows can then share that same alternative parameter.

The initial override value is copied from the source standard Global Parameter.

!!! info "Existing Window workflow"

    The documented shared-override workflow is based on the Existing Window head-height standard.

    It allows a controlled group of Existing Windows to share one alternative value.

---

## Assign an Existing Head Height Parameter

A selected Window can also be assigned to an existing recognised head-height Global Parameter.

The documented workflow provides compatible head-height parameters, including the standard parameter and recognised override parameters.

If the Window already uses the selected Global Parameter, that association can remain unchanged.

If it uses another compatible association, the selected head-height parameter can replace it.

---

## Remove an Individual Override

Use **Remove Override** when an individually overridden Window should return to the normal head-height control.

The documented removal workflow restores the Window to:

```text
Window Head Height
```

If that standard Global Parameter is missing, the workflow can create it.

If the Window currently has no Global Parameter association, the operation can also repair the missing standard association.

---

## Recognised Individual Overrides

The documented individual removal workflow only treats associations following this naming pattern as Flow head-height overrides:

```text
Window Head Height_...
```

An unrelated Global Parameter is not automatically treated as a removable Flow override.

This helps protect other project associations from being removed accidentally.

---

## Standard vs Override

A typical individual New Window setup might be:

```text
Window Head Height
    ├── W01
    ├── W02
    └── W04

Window Head Height_W03
    └── W03
```

The normal project parameter continues to control W01, W02 and W04, while W03 has its own controlled exception.

A shared Existing Window exception might be:

```text
X-Window Head Height
    ├── Wx01
    └── Wx02

X-Window Head Height_Lower
    ├── Wx03
    └── Wx04
```

Wx03 and Wx04 can then be adjusted together without changing the standard Existing Window head height.

---

## When to Use an Override

Use an override when:

- one Window needs a different head height from the project standard
- a controlled group of Existing Windows needs to share an alternative head height
- a Window needs to be assigned to an existing recognised head-height Global Parameter

Do not create an override when the project-wide standard itself is wrong.

In that case, change the appropriate standard Global Parameter instead.

---

## After Changing an Override

After creating, assigning or removing an override:

1. review the affected Window in Revit
2. confirm the required Global Parameter association
3. adjust the override value where required
4. return to Openings Manager
5. use **Refresh** where the register needs to be rebuilt
6. review the **Head Height GP** status

!!! note "Refresh also applies the zero-sill rule"

    In the current Openings Manager implementation, **Refresh** is not read-only.

    It applies the `Sill Height` → `Zero Window Sill Height` Window rule before rebuilding the register.

This zero-sill operation is separate from the head-height override itself.

---

## If an Override Cannot Be Removed

Check that the Window is actually associated with a recognised Flow individual override.

The documented removal workflow expects the current Global Parameter to follow:

```text
Window Head Height_...
```

If the Window uses an unrelated Global Parameter, Flow does not treat that association as a removable individual Flow override.

For wider association review, use **Parameters Manager**.

➡️ [**Opening Global Parameters**](opening-global-parameters.md)

➡️ [**Openings Manager Troubleshooting**](troubleshooting.md)

---

## Related Help

- [**Opening Global Parameters**](opening-global-parameters.md)
- [**Reviewing Openings**](reviewing-openings.md)
- [**Openings Manager Troubleshooting**](troubleshooting.md)
