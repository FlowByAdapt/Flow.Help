# Project Information

Project Information allows supported project metadata stored in the
active Revit project to be inspected, reviewed and updated as part of
Project Setup.

It is distinct from **Project Identity**, which contains shared values
used by Project Setup workflows.

------------------------------------------------------------------------

## Opening Project Information

Open:

**Flow → Project → Setup**

Inspect the current project, then open the **Project Information**
review.

------------------------------------------------------------------------

## Inspection

Project Setup reads supported Project Information parameters and reports
their current state.

Inspection does not overwrite existing values.

!!! info "Inspection does not change Project Information"

    Changes are only written when you deliberately apply the proposed edits.

------------------------------------------------------------------------

## Reviewing and Editing Values

The review presents current values and allows proposed values to be
entered before anything is written back to Revit.

Supported information is grouped into configured sections, including
project, internal-team, external-team and site-information fields.

!!! tip "Review before applying"

    Check proposed values carefully before applying them.

------------------------------------------------------------------------

## Parameter Checks

Project Setup can identify a supported field where the required
parameter:

-   exists and can be edited;
-   is missing; or
-   is read-only or otherwise unavailable for modification.

!!! warning "Parameter unavailable?"

    Do not create an ad-hoc replacement parameter merely to clear the status. Review or report the configuration problem.

------------------------------------------------------------------------

## Applying Changes

Apply the reviewed changes when you are satisfied with the proposed
values.

Re-inspect the project when required to confirm the resulting Project
Information state.

------------------------------------------------------------------------

## Project Identity Is Different

Project Identity contains **Project Year**, **Project Number**,
**Client** and **Location** and is used by workflows such as folder
planning and new-project creation.

Project Information represents supported information stored in the
active Revit model.

➡️ **[Project Identity →](project-identity.md)**

------------------------------------------------------------------------

## Related Help

-   [Project Setup](index.md)
-   [Project Identity](project-identity.md)
-   [Creating a New Project](new-projects.md)
-   [Reviewing a Current Project](current-projects.md)
-   [Project Folders](project-folders.md)
-   [Troubleshooting](troubleshooting.md)
