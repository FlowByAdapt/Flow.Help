# Worksets

The Worksets section checks the worksets in the current Revit project
against the worksets expected by Flow.

This helps ensure that workshared projects use a consistent office-standard
workset structure.

---

## Opening Worksets

Open:

**Flow → Project → Setup**

Open the **Worksets** section.

Flow inspects the worksets currently present in the Revit project.

!!! info "Inspection does not change the project"

    Workset inspection only checks the current workset configuration.

    Worksets are only created when you choose to apply the relevant
    Project Setup action.

---

## Inspection Results

The inspection identifies whether the expected worksets are already present.

Existing worksets that satisfy the expected configuration are reported as
complete.

Missing worksets are identified for review.

---

## Creating Missing Worksets

Where required, Project Setup can create missing office-standard worksets.

Review the inspection results before applying the changes.

Flow creates the required worksets through the Project Setup workflow.

!!! note "Existing worksets are preserved"

    Project Setup creates required worksets that are missing.

    Existing worksets are not recreated simply because you run the
    workset setup again.

---

## Existing Worksets

Project Setup is intended to help establish the required workset structure
without unnecessarily changing existing project content.

Existing project worksets should therefore be reviewed before making
structural changes to a live project.

!!! warning "Existing project worksets"

    Project Setup checks for the worksets required by Flow, but existing
    project-specific worksets may also be present.

    Review the current workset structure before making other manual changes
    to worksets in a live project.

---

## Non-Workshared Projects

Workset configuration only applies to workshared Revit projects.

!!! note "Worksharing required"

    If the current project is not workshared, Flow cannot inspect or create
    the required project worksets.

    Enable Revit worksharing before completing the Worksets section of
    Project Setup.

---

## Refreshing the Results

After worksets have been created or changed, use **Refresh** to run the
Project Setup inspection again.

The inspection results should then reflect the current workset configuration.

!!! tip "Changed a workset directly in Revit?"

    Use **Refresh** after making workset changes outside Project Setup.

    This updates the inspection results without needing to close and reopen
    Project Setup.

---

## Related Help

- [Project Setup](index.md)
- [Reviewing a Current Project](current-projects.md)
- [Project Information](project-information.md)
- [Project Folders](project-folders.md)
- [Troubleshooting](troubleshooting.md)