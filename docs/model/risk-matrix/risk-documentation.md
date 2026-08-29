# Risk Documentation

Risk Matrix stores coordinated information in the Revit model so Risk
Faces can be represented consistently in project documentation.

The current workflow uses wall parameters, Risk Face tags, Risk View
graphics and project cladding information.

------------------------------------------------------------------------

## Risk Face Parameters

When walls are processed, Risk Matrix writes information to the wall
elements, including the Risk Face assignment and the applicable Risk
Matrix values.

This allows the information to be used by Revit schedules, tags and
other parameter-driven documentation already configured in the project.

Risk Matrix does not currently provide a separate completed-results grid
that replaces Revit documentation.

------------------------------------------------------------------------

## Risk Face Tags

Risk Matrix automatically uses:

**ADa_TAG_Wall_Risk : Risk Face label**

A tag is placed on a representative wall for a Risk Face in the current
view where possible.

Risk Matrix checks for an existing Risk Matrix tag for the face before
creating another one.

Tags are also managed when faces are copied or reset.

------------------------------------------------------------------------

## Risk View Colours

Processed walls receive view-specific graphical overrides.

Each Risk Face number is assigned a distinct colour together with
consistent projection line graphics.

These overrides are intended to make the Risk Faces easy to distinguish
while reviewing and documenting the building envelope.

!!! info "The colour represents the Risk Face"

    The colour identifies the Risk Face number.

    It does not represent the calculated E2 risk score.

------------------------------------------------------------------------

## Matching Wall-End Graphics

At wall junctions, the visible end of another wall may interrupt the
coloured face.

Use:

**Match Wall End**

to apply the source Risk Face graphics to the target wall in the current
view.

This is a documentation/presentation adjustment only. The target wall is
not assigned to the source Risk Face and its Risk Matrix parameters are
not changed.

------------------------------------------------------------------------

## Cladding Documentation

Risk Matrix maintains a project-wide cladding configuration based on the
exterior wall types discovered in the model. Included wall types are mapped to
a coordinated cladding description and one of four project slots:

-   **RM - Cladding 1**
-   **RM - Cladding 2**
-   **RM - Cladding 3**
-   **RM - Cladding 4**

Wall types with matching cladding descriptions are coordinated into the same
slot. Unused slots are set to:

**N/A**

The associated wall **Cladding Category** identifies which project slot applies
to that wall when Risk Faces are processed.

The project cladding setup is stored in the Revit model, including included or
excluded wall types, edited descriptions and selected cladding groups. It is
restored when Risk Matrix is reopened.

This provides stable coordinated model information that can be consumed by
project documentation without requiring the cladding setup to be recreated for
each Risk View or session.

!!! warning "Maximum four cladding types"

    The current Risk Matrix cladding workflow supports up to four coordinated project cladding descriptions.

## Risk Views

Risk Matrix recognises section/elevation views whose names begin with:

**RISK-**

The default Risk View is:

**RISK-01-Elevation**

Use **Previous View** and **Next View** to move through the available
Risk Views in name order.

The Risk Face graphics and tags are view-based, so review the relevant
Risk Views as part of the documentation check.

------------------------------------------------------------------------

## Resetting Documentation

Resetting an individual Risk Face removes its Risk Matrix wall
information, relevant Risk Face graphics and tags before the remaining
faces are renumbered. The project cladding configuration is preserved.

**Reset Risk Matrix** performs a project-wide cleanup of Risk Matrix
wall/project parameters, Risk Face graphical overrides, Risk Matrix tags
and face-numbering state. It also clears the saved project cladding
configuration. Risk Matrix then rebuilds the Cladding tab from the automatic
wall-type discovery and default mappings.

!!! warning "Reset Risk Matrix is a broad reset"

    Use the individual face-reset workflow where possible when correcting a local issue.

    Use **Reset Risk Matrix** when the Risk Matrix information needs to be cleared across the project.

------------------------------------------------------------------------

## Risk Schedules and Final Scores

The current implementation prepares parameter-driven Risk Matrix
information that can be used by Revit documentation.

Automated per-face E2 scoring and a dedicated completed-results review
interface are not yet part of the current Risk Matrix tool.

------------------------------------------------------------------------

## Related Help

-   [Risk Matrix](index.md)
-   [Identifying Risk Faces](identifying-risk-faces.md)
-   [Assigning Risk Information](assigning-risk-information.md)
-   [Reviewing Risk Results](reviewing-risk-results.md)
-   [Troubleshooting](troubleshooting.md)