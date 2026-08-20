# Project Information

Project Information allows important project metadata to be reviewed and
maintained as part of the Project Setup workflow.

This keeps project information together with the other project setup tasks
rather than requiring separate setup tools.

---

## Opening Project Information

Open:

**Flow → Project → Setup**

Open the **Project Information** section for the current project.

---

## Existing Values

Flow reads the existing project information from the Revit project and
displays the current values.

This allows existing projects to be reviewed without replacing information
that has already been entered.

!!! info "Existing information is not changed during inspection"

    Opening or refreshing Project Information reads the current values from
    the Revit project.

    Project information is only modified when you choose to apply the
    proposed changes.

---

## Editing Project Information

Update the required fields within Project Setup.

Changes are shown as proposed values before they are applied to the Revit
project.

This allows the information to be reviewed before modifying the model.

!!! tip "Review before applying"

    Check the proposed values before applying the changes, particularly
    project identification information such as the project number and
    project name.

---

## Parameter Checks

Project Setup can identify situations where a required project information
parameter:

- exists and can be edited;
- is missing; or
- cannot currently be modified.

This helps identify configuration problems rather than silently ignoring
missing project information.

!!! warning "Parameter unavailable?"

    If a required parameter is missing or cannot be modified, Project Setup
    cannot write the proposed value to that parameter.

    Review the reported status before applying the remaining project
    information changes.

---

## Applying Changes

Review the proposed project information before applying the changes.

Only the appropriate project information values are written back to the
Revit project.

After the changes are applied, the Project Setup inspection can be refreshed
to confirm the current project information.

---

## New Projects

Project information is also used during the new-project workflow.

Some information may be used elsewhere in Project Setup, including project
identification and project folder creation.

!!! note "Project information is used elsewhere"

    Project information is not only stored in the Revit model.

    Values such as the project number and project name may also be used by
    other Project Setup workflows, including project folder naming and
    project creation.

    Confirm these values are correct before continuing with related setup tasks.

---

## Related Help

- [Project Setup](index.md)
- [Creating a New Project](new-projects.md)
- [Reviewing a Current Project](current-projects.md)
- [Project Folders](project-folders.md)
- [Troubleshooting](troubleshooting.md)