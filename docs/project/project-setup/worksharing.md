# Worksharing

The Worksharing section checks whether the active Revit project is
workshared.

Worksharing is required before Project Setup can configure the standard
project worksets.

------------------------------------------------------------------------

## Inspect Worksharing

Open:

**Flow → Project → Setup**

Select **Inspect Project**.

Project Setup reports the current Worksharing state. Inspection itself
does not enable worksharing.

------------------------------------------------------------------------

## Project Is Already Workshared

If worksharing is already enabled, the Worksets workflow can inspect the
required project worksets.

➡️ **[Worksets →](worksets.md)**

------------------------------------------------------------------------

## Project Is Not Workshared

If the active project is not workshared, Project Setup can make **Enable
Worksharing** available.

Use that action when the project is intended to use the standard
workshared workflow.

Enabling worksharing changes the Revit project and occurs only when you
deliberately choose the action.

------------------------------------------------------------------------

## After Enabling Worksharing

Inspect the project again as required.

The Worksets section can then compare the active project with the
expected workset configuration.

!!! tip "Worksharing comes before Worksets"

    Complete Worksharing first when Worksets cannot be configured because the project is not workshared.

------------------------------------------------------------------------

## Related Help

-   [Project Setup](index.md)
-   [Reviewing a Current Project](current-projects.md)
-   [Worksets](worksets.md)
-   [Troubleshooting](troubleshooting.md)
