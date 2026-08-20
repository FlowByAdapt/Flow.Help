# Opening Global Parameters

Flow uses Revit Global Parameters to maintain several standard Window
and Door behaviours across the project.

Openings Manager audits these associations so that missing or incomplete
setup can be identified and corrected.

------------------------------------------------------------------------

## Why Global Parameters Are Used

Global Parameters allow multiple opening instances to share controlled
project values.

Flow uses these associations for standards such as:

-   Window sill height
-   Window head height
-   Door 3D display
-   Door trim display
-   Architrave dimensions
-   Door plan opening
-   Door panel opening angle

This reduces the need to manage the same setting independently on every
opening.

------------------------------------------------------------------------

## Global Parameter Status

The Openings Manager register can report the state of the expected
opening Global Parameter setup.

Depending on the opening, the status can identify whether the required
associations are complete, missing, not configured or not required.

Use the register to identify openings that need attention.

➡️ [**Reviewing Openings**](reviewing-openings.md)

------------------------------------------------------------------------

## Window Sill Height

Flow's standard Window setup associates the Window instance parameter:

``` text
Sill Height
```

with the project Global Parameter:

``` text
Zero Window Sill Height
```

This is the mechanism used to maintain the standard zero-sill setup.

------------------------------------------------------------------------

## Window Head Height

Window head heights use standard project Global Parameters.

The normal associations are:

  Window     Global Parameter
  ---------- ------------------------
  New        `Window Head Height`
  Existing   `X-Window Head Height`

Individual or grouped exceptions can be managed using Window Head Height
Overrides.

➡️ [**Window Head Height Overrides**](head-height-overrides.md)

------------------------------------------------------------------------

## Door Global Parameters

For New Construction doors, Flow recognises several standard family
parameters and associates them with shared project Global Parameters.

The supported rules include:

  Door Family Parameter        Global Parameter
  ---------------------------- ---------------------------
  `Allow Door to Open in 3d`   `3D Doors Show`
  `Open 3d Panels`             `3D Doors Show`
  `3D Doors Show`              `3D Doors Show`
  `Show External Trim`         `Interior Door Trim Show`
  `Show Internal Trim`         `Interior Door Trim Show`
  `Interior Door Trim Show`    `Interior Door Trim Show`
  `Architrave_Depth`           `Architrave_Depth`
  `Architrave_Width`           `Architrave_Width`
  `Plan % Open`                `Plan % Open`
  `3d Panel Opening Angle`     `3d Panel Opening Angle`

Different approved Door families can therefore use alternative family
parameter names while still being controlled by the same project
standard.

------------------------------------------------------------------------

## Default Architrave Values

If the standard Architrave Global Parameters need to be created, Flow
gives the new Length parameters the following initial values:

``` text
Architrave_Depth = 20 mm
Architrave_Width = 60 mm
```

This prevents newly associated architrave geometry from being driven by
a zero-length Global Parameter.

------------------------------------------------------------------------

## Plan Opening Default

If Flow creates the standard:

``` text
Plan % Open
```

Global Parameter, its initial value is:

``` text
40
```

------------------------------------------------------------------------

## Existing Global Parameters

Flow first checks whether the required Global Parameter already exists.

If it exists, Flow uses the existing parameter rather than creating a
duplicate.

Similarly, if an opening parameter is already associated with a Global
Parameter, the standard association operation does not simply overwrite
that existing association.

!!! info "Existing associations are protected"

    The standard Global Parameter setup is intended to establish missing project standards.

    It does not indiscriminately replace existing Global Parameters or existing parameter associations.

------------------------------------------------------------------------

## New Construction Doors

The standard Door Global Parameter rules are applied to **New
Construction** doors.

Existing and other non-New door instances are not processed by the
standard New-door association rules.

------------------------------------------------------------------------

## Parameters Manager

Opening Global Parameters are part of the wider project Global Parameter
system.

Use the dedicated **Parameters Manager** when you need to review or
manage the project's Global Parameters and associations beyond the
opening-specific workflows provided by Openings Manager.

------------------------------------------------------------------------

## Head Height Exceptions

Do not break the standard Window head-height setup simply to create an
exception.

Use Flow's dedicated override tools instead.

These allow a Window to use an alternative Global Parameter while
preserving a controlled project workflow.

➡️ [**Window Head Height Overrides**](head-height-overrides.md)

------------------------------------------------------------------------

## Related Help

-   [**Reviewing Openings**](reviewing-openings.md)
-   [**Door Heights**](door-heights.md)
-   [**Window Head Height Overrides**](head-height-overrides.md)
-   [**Openings Manager Troubleshooting**](troubleshooting.md)