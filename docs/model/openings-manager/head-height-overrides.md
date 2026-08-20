# Window Head Height Overrides

Use Window Head Height Overrides when one or more windows need a head
height that differs from the normal project standard.

Flow manages these exceptions using dedicated Global Parameter
associations rather than disconnecting the window from the project
control system.

------------------------------------------------------------------------

## Standard Head Height Associations

The normal Window head-height Global Parameters are:

  Window     Standard Global Parameter
  ---------- ---------------------------
  New        `Window Head Height`
  Existing   `X-Window Head Height`

Overrides allow selected windows to use a separate controlled value
while the remaining windows continue to follow the standard project
parameter.

------------------------------------------------------------------------

## Individual Override

Use an individual override when a single window needs its own
head-height control.

Flow:

1.  checks the Window's current standard association
2.  repairs the standard association first if it is missing
3.  creates or finds the required override Global Parameter
4.  copies the current standard value into the override
5.  associates the selected Window with the override

Because the current standard value is copied into the new override,
creating the override does not by itself change the Window's head
height.

You can then adjust the override value independently.

!!! tip "Create the override before changing the value"

    The override begins with the current standard head-height value.

    This separates the Window from the standard control without immediately moving the opening.

------------------------------------------------------------------------

## Shared Override

Use a shared override when several windows need to use the same
alternative head height.

The shared override workflow allows you to provide an override suffix.

Flow uses that suffix to create a shared Global Parameter name in the
form:

``` text
X-Window Head Height_<suffix>
```

The selected windows can then be associated with the same override
parameter.

The initial override value is copied from the source standard Global
Parameter.

!!! info "Shared overrides"

    The current shared-override workflow is based on the Existing Window head-height standard.

    It provides a controlled way for multiple Existing windows to share one alternative head-height value.

------------------------------------------------------------------------

## Assign an Existing Head Height Global Parameter

You can also assign selected windows to an existing head-height Global
Parameter.

Flow provides the available recognised head-height parameters, including
the standard parameter and compatible override parameters.

If a Window already uses the selected Global Parameter, Flow leaves that
association in place.

If it uses another Global Parameter, Flow can replace that association
with the selected head-height parameter.

------------------------------------------------------------------------

## Remove an Individual Override

Use **Remove Override** when a Window should return to the standard
head-height control.

Flow restores the Window to:

``` text
Window Head Height
```

If the standard Global Parameter is missing, Flow can create it.

If the Window has no current Global Parameter association, the operation
can repair the missing standard association.

------------------------------------------------------------------------

## Recognised Overrides

Flow only removes an association as an individual Flow head-height
override when it follows the recognised override naming pattern:

``` text
Window Head Height_...
```

An arbitrary Global Parameter is not treated as a Flow override.

This protects unrelated project Global Parameter associations from being
removed accidentally.

------------------------------------------------------------------------

## When to Use an Override

Use a head-height override when:

-   one Window needs a different head height from the project standard
-   a controlled group of Existing windows needs to share an alternative
    head height
-   an existing recognised head-height Global Parameter should be
    assigned to selected windows

Do not use an override where the project-wide standard itself should
change.

In that case, update the appropriate standard Global Parameter instead.

------------------------------------------------------------------------

## Standard vs Override

A typical setup might be:

``` text
Window Head Height
    ├── W01
    ├── W02
    └── W04

Window Head Height_W03
    └── W03
```

The standard parameter continues to control the normal windows while W03
has its own controlled exception.

For a shared Existing-window exception:

``` text
X-Window Head Height
    ├── Wx01
    └── Wx02

X-Window Head Height_Lower
    ├── Wx03
    └── Wx04
```

------------------------------------------------------------------------

## After Changing Overrides

After creating, assigning or removing a head-height override:

1.  review the affected Window in Revit
2.  confirm that the required Global Parameter association is in place
3.  adjust the override value if required
4.  refresh Openings Manager
5.  review the updated Global Parameter status

------------------------------------------------------------------------

## If an Override Cannot Be Removed

Check that the Window is actually associated with a recognised Flow
override.

The individual override removal workflow expects the current Global
Parameter to follow:

``` text
Window Head Height_...
```

If the Window uses an unrelated Global Parameter, Flow does not treat
that association as a removable Flow override.

For further checks:

➡️ [**Openings Manager Troubleshooting**](troubleshooting.md)

------------------------------------------------------------------------

## Related Help

-   [**Opening Global Parameters**](opening-global-parameters.md)
-   [**Reviewing Openings**](reviewing-openings.md)
-   [**Openings Manager Troubleshooting**](troubleshooting.md)