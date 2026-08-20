# Reviewing Risk Faces

Use Risk Matrix and the Revit Risk Views to review the Risk Faces and
model information created by the current workflow.

The current version does not yet provide a completed per-face E2
scoring/results grid.

------------------------------------------------------------------------

## Review the Risk Views

Use **Previous View** and **Next View** in Risk Matrix to move through
views whose names begin with:

**RISK-**

Review each elevation and check that the building envelope has been
divided into the intended Risk Faces.

------------------------------------------------------------------------

## Check Face Numbers

Each processed face is identified as:

**Face 1**, **Face 2**, **Face 3** and so on.

A Risk Face can contain several Revit walls where the walls form one
coplanar and continuous building face.

Check that:

-   walls that should form one face share the same number;
-   genuine breaks or changes of plane have separate numbers;
-   the numbering sequence is sensible; and
-   previously processed faces have not been unintentionally reassigned.

------------------------------------------------------------------------

## Check Face Colours

Each Risk Face is given a distinct colour in the Risk View.

Use the colours to quickly identify which wall segments belong to the
same Risk Face.

!!! note "Colours identify faces, not risk scores"

    Risk Face colours are graphical identifiers for the face number.

    They do not indicate low, medium or high E2 risk and should not be interpreted as a completed risk result.

------------------------------------------------------------------------

## Check Risk Face Tags

Risk Matrix places the tag:

**ADa_TAG_Wall_Risk : Risk Face label**

on a representative wall for each processed Risk Face where the tag can
be created.

Check that each required face has a clear label and that duplicate or
obsolete labels have not remained after editing.

------------------------------------------------------------------------

## Check the Assigned Information

Processed walls receive the Risk Matrix values that were active when
they were processed.

Where required, review the wall parameters and confirm that the expected
information has been applied.

Pay particular attention where different building faces require
different values for:

-   Number of Storeys;
-   Roof / Wall;
-   Eave Width;
-   Envelope; or
-   Deck.

Wind Zone is sourced from the project-wide **Project Information → Wind
Zone** value.

------------------------------------------------------------------------

## Review Cladding Coordination

Open the **Cladding** tab and review:

### Project Cladding Legend

Shows up to four cladding descriptions used by processed walls.

Unused slots are shown as **N/A**.

### Wall Type Cladding Mapping

Review the cladding description associated with the relevant wall types.

Risk Matrix normalises the processed wall information so that each
recognised description is assigned to a coordinated project cladding
slot.

The current implementation supports a maximum of **four unique cladding
types**.

------------------------------------------------------------------------

## Correcting a Face

Use the appropriate correction workflow rather than rebuilding the
entire Risk Matrix where possible.

**Copy Face**\
Use when a wall should inherit an existing Risk Face assignment and Risk
Matrix/cladding data.

**Match Wall End**\
Use when only the displayed Risk Face colour needs to continue onto
another wall.

**Reset selected face**\
Use the face-reset workflow when an existing Risk Face needs to be
cleared and recreated. Remaining faces are renumbered to close the gap.

**Reset Risk Matrix**\
Use only when the project-wide Risk Matrix information needs to be
cleared.

------------------------------------------------------------------------

## About Final Risk Results

Automated E2 face scoring is not currently part of this Risk Matrix
interface.

The present review workflow verifies the Risk Face geometry, numbering,
tags, colours, project values and cladding coordination that support the
assessment documentation.

!!! info "Future scoring workflow"

    A later Risk Matrix development stage is intended to provide face-specific suggested values, user confirmation and calculated risk results.

------------------------------------------------------------------------

## Related Help

-   [Risk Matrix](index.md)
-   [Identifying Risk Faces](identifying-risk-faces.md)
-   [Assigning Risk Information](assigning-risk-information.md)
-   [Risk Documentation](risk-documentation.md)
-   [Troubleshooting](troubleshooting.md)