# Worksets

The Worksets section checks the worksets in the active Revit project
against the worksets expected by the configured Flow workflow.

------------------------------------------------------------------------

## Inspect Worksets

Open:

**Flow → Project → Setup**

Select **Inspect Project**.

If the project is workshared, Project Setup compares the current
worksets with the expected configuration.

!!! info "Inspection does not change the project"

    Missing worksets are created only when you deliberately choose the relevant setup action.

------------------------------------------------------------------------

## Inspection Results

Existing required worksets contribute to a complete state. Missing
required worksets are reported for review.

------------------------------------------------------------------------

## Configure Missing Worksets

Where required, Project Setup can create the missing office-standard
worksets.

Existing required worksets are preserved rather than recreated.

!!! note "Existing worksets are preserved"

    Project Setup adds required worksets that are missing. It does not recreate a required workset simply because it already exists.

------------------------------------------------------------------------

## Existing Project-Specific Worksets

A live project may contain additional project-specific worksets beyond
those required by Flow.

Project Setup checks for its expected worksets; it is not an instruction
to remove unrelated existing worksets.

------------------------------------------------------------------------

## Non-Workshared Projects

Workset configuration requires a workshared Revit project.

If worksharing is appropriate, complete the **Worksharing** step first.
Project Setup can enable worksharing when the action is available.

➡️ **[Worksharing →](worksharing.md)**

------------------------------------------------------------------------

## Re-inspection

After configuring worksets, inspect or refresh the project as required
so the displayed state reflects the resulting configuration.

------------------------------------------------------------------------

## Related Help

-   [Project Setup](index.md)
-   [Reviewing a Current Project](current-projects.md)
-   [Worksharing](worksharing.md)
-   [Project Information](project-information.md)
-   [Project Folders](project-folders.md)
-   [Troubleshooting](troubleshooting.md)
