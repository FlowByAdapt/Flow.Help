# Reviewing Risk Results

After processing the building faces, review the Risk Views and model
information before relying on the Risk Matrix documentation.

The current review is a check of **Risk Face mapping and assigned
information**. Automated completed E2 scoring is not yet part of this
interface.

------------------------------------------------------------------------

## Review Every Risk View

Use **Previous View** and **Next View** to work through the available
**RISK-** views.

For each view, confirm:

-   all required exterior building faces have been processed;
-   Risk Face boundaries make sense;
-   face numbering follows the intended sequence;
-   colours are consistent with the face numbers;
-   Risk Face labels are present where expected; and
-   exposed wall ends are graphically coordinated where required.

<!-- SCREENSHOT: Completed Risk View showing several Risk Faces, tags and wall-end graphics. -->

------------------------------------------------------------------------

## Review Face Grouping

A Risk Face may contain multiple Revit walls.

Check vertically split or segmented walls carefully to confirm that
walls forming one continuous building face have been grouped together
and that genuine changes of plane have not been combined incorrectly.

If a face needs to be rebuilt, use the selected-face reset rather than
manually editing Risk Face parameters.

------------------------------------------------------------------------

## Review Risk Values

Where required, inspect the wall parameters and confirm the expected
values have been applied.

Pay particular attention where different building faces require
different values for:

-   **Number of Storeys**
-   **Roof / Wall**
-   **Eave Width**
-   **Envelope**
-   **Deck**

Wind Zone is sourced from the project-wide **Project Information → Wind
Zone** value.

Already processed walls are protected from having these stored values
overwritten merely because they are selected again.

------------------------------------------------------------------------

## Review Cladding Coordination

Open the **Cladding** tab and review the project-wide configuration.

### Project Cladding Legend

Confirm that the **Cladding 1--4** descriptions represent the intended
project claddings. Unused slots should show **N/A**.

### Wall Types to Include

Confirm that required exterior wall types are included and irrelevant
types are excluded.

Review the description and assigned group for each included type. Wall
types sharing the same cladding description should normally share the
same cladding group.

### Wall Type Cladding Mapping

Check the resulting relationship between Revit wall types and
coordinated project cladding descriptions.

### Project Cladding Health

Resolve unexpected descriptions or group assignments before relying on
the cladding information in project documentation.

The current workflow supports a maximum of **four unique coordinated
cladding descriptions**.

!!! info "Cladding setup is persistent"

    Included wall types, edited descriptions and group selections are stored with the Revit project and restored when Risk Matrix is reopened.

------------------------------------------------------------------------

## Correcting a Face

Use the correction workflow that matches the problem.

**Copy Face**\
Use when one or more walls should genuinely inherit an existing Risk
Face assignment and its Risk Matrix/cladding data.

**Match Wall End**\
Use when only the displayed Risk Face graphics need to continue onto an
exposed wall end.

**Reset Selected Face**\
Use when one Risk Face needs to be cleared and recreated. The
project-wide cladding setup is preserved.

**Reset Risk Matrix**\
Use only when the complete project Risk Matrix information needs to be
cleared. A full reset also clears the saved cladding setup.

------------------------------------------------------------------------

## Reprocessing a Reset Face

When a previously reset face is selected again, Flow may recognise its
former number.

If the **Risk Face Number** dialog appears, decide whether to:

-   use **Next Available**;
-   **Restore Original**; or
-   **Choose Number...**

Restoring or inserting a number can shift later Risk Faces to maintain a
coordinated sequence.

------------------------------------------------------------------------

## About Final Risk Results

Automated E2 face scoring is not currently part of this Risk Matrix
interface.

The present review workflow verifies the Risk Face geometry, numbering,
tags, colours, assigned project values and cladding coordination that
support the assessment documentation.

!!! info "Future scoring workflow"

    A later development stage is intended to provide face-specific suggestions, architect confirmation and calculated risk results.

------------------------------------------------------------------------

## Related Help

-   [**Risk Matrix**](index.md)
-   [**Identifying Risk Faces**](identifying-risk-faces.md)
-   [**Assigning Risk Information**](assigning-risk-information.md)
-   [**Risk Documentation**](risk-documentation.md)
-   [**Troubleshooting**](troubleshooting.md)
