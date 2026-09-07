# Risk Documentation

Risk Matrix stores coordinated information in the Revit model so Risk
Faces can be represented consistently in project documentation.

The current workflow uses wall parameters, Risk Face tags, Risk View
graphics and project cladding information.

------------------------------------------------------------------------

## Risk Face Parameters

When new walls are processed, Risk Matrix writes the Risk Face
assignment and applicable Risk Matrix values to the wall elements.

This allows the information to be consumed by Revit schedules, tags and
other parameter-driven documentation configured in the project.

Risk Matrix does not currently provide a separate completed-results grid
that replaces Revit documentation.

------------------------------------------------------------------------

## Risk Face Tags

Risk Matrix uses:

**ADa_TAG_Wall_Risk : Risk Face label**

A tag is placed on a representative wall for a Risk Face in the current
view where possible.

Risk Matrix checks for an existing Risk Matrix tag before creating
another one. Tags are also managed when faces are copied or reset.

------------------------------------------------------------------------

## Risk View Colours

Processed walls receive view-specific graphical overrides.

Each Risk Face number is assigned a distinct colour together with
coordinated projection line graphics.

!!! info "The colour represents the Risk Face"

    The colour identifies the Risk Face number. It does not represent the calculated E2 risk score.

------------------------------------------------------------------------

## Matching Wall-End Graphics

At wall junctions, the visible end of another wall may interrupt the
coloured Risk Face.

Use **Match Wall End** to:

1.  select the processed Risk Face whose colour should be used; then
2.  select the exposed target **wall face**.

The operation applies presentation graphics in the active view only. It
does not assign the target wall to the source Risk Face or copy its Risk
Matrix parameters.

------------------------------------------------------------------------

## Cladding Documentation

Risk Matrix maintains a project-wide cladding configuration based on
discovered exterior wall types.

Included wall types are mapped to a coordinated cladding description and
one of four project slots:

-   **RM - Cladding 1**
-   **RM - Cladding 2**
-   **RM - Cladding 3**
-   **RM - Cladding 4**

Unused slots are represented as **N/A**.

The associated wall **Cladding Category** identifies which project slot
applies when the wall is processed.

The project cladding setup stores included/excluded wall types, edited
descriptions and selected groups in the Revit project so the setup can
be restored in later sessions.

!!! warning "Maximum four cladding types"

    The current Risk Matrix cladding workflow supports up to four coordinated project cladding descriptions.

------------------------------------------------------------------------

## Risk Views

Risk Matrix recognises section/elevation views whose names begin with:

**RISK-**

The default Risk View is:

**RISK-01-Elevation**

Use **Previous View** and **Next View** to move through the available
Risk Views.

Risk Face graphics and tags are view-based, so review every relevant
Risk View as part of the documentation check.

------------------------------------------------------------------------

## Resetting Documentation

### Selected Risk Face

Resetting one Risk Face clears that face's:

-   Risk values;
-   Risk Face name;
-   cladding values and category;
-   Risk View graphic overrides; and
-   associated Risk Wall tags.

Other processed faces and the project-wide cladding setup are preserved.

### Entire Project

A full **Reset Risk Matrix** performs a project-wide cleanup of Risk
Matrix wall/project information, Risk Face graphical overrides, Risk
Matrix tags and face-numbering state.

It also clears the saved project cladding configuration.

!!! warning "Reset Risk Matrix is a broad reset"

    Use the selected-face reset for local corrections wherever possible.

------------------------------------------------------------------------

## Risk Schedules and Final Scores

The current implementation prepares parameter-driven Risk Matrix
information for Revit documentation.

Automated per-face E2 scoring and a dedicated completed-results review
interface are not yet part of the current tool.

------------------------------------------------------------------------

## Related Help

-   [**Risk Matrix**](index.md)
-   [**Identifying Risk Faces**](identifying-risk-faces.md)
-   [**Assigning Risk Information**](assigning-risk-information.md)
-   [**Reviewing Risk Results**](reviewing-risk-results.md)
-   [**Troubleshooting**](troubleshooting.md)
