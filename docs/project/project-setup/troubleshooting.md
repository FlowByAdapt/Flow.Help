# Project Setup Troubleshooting

Use this page to resolve common issues encountered while using **Project Setup**.

Project Setup performs a number of checks against the current Revit project,
project configuration and external project locations. Some options may therefore
be unavailable until the required project information or conditions are present.

---

## Project Setup Will Not Open

If Project Setup does not open from the Flow ribbon:

1. Confirm that the **Flow** ribbon has loaded correctly.
2. Check whether other Flow tools open normally.
3. Close and restart Revit.
4. Try opening Project Setup again.

If other Flow tools are also unavailable, the issue may relate to the Flow
installation rather than Project Setup itself.

---

## Create Project Is Disabled

The **Create Project** button remains unavailable until Project Setup has enough
information to create a valid project.

Check that:

- a valid **Project Profile** has been selected;
- the required project information has been entered;
- the selected profile is available for the current Revit version; and
- the required Revit template is available.

If a required selection is missing, complete that selection before continuing.

➡️ **[Creating a New Project](new-projects.md)**

---

## Project Profile Is Not Available

Project profiles are filtered according to the current Revit version and the
configuration available to Project Setup.

If the expected profile does not appear:

1. Confirm that you are using the intended version of Revit.
2. Check the available profiles in the Project Setup window.
3. Confirm that the required office template is available for that Revit version.

If the profile should be available but is still missing, report the issue to
the Flow administrator.

---

## Project Template Is Not Available

Flow uses the selected Project Profile to determine the appropriate
office-approved Revit template.

If the required template cannot be found, project creation may not be available.

Check that:

- the correct Project Profile has been selected;
- the appropriate template exists for the current Revit version; and
- the office Revit library is accessible.

!!! warning "Don't substitute another template"

    Do not select an unrelated Revit template simply to continue the setup process.

    The Project Profile is intended to ensure that the project starts from the
    appropriate office-approved template for the current Revit version.

---

## Project Information Is Incomplete

Project Setup checks the required project information before applying changes
or using that information elsewhere in the setup workflow.

If information is reported as incomplete:

1. Open the **Project Information** section.
2. Review the current and proposed values.
3. Complete any required information.
4. Apply the changes.
5. Refresh the Project Setup inspection.

➡️ **[Project Information](project-information.md)**

---

## A Project Information Field Cannot Be Changed

Some project information fields may be unavailable for editing.

Project Setup may identify a field where:

- the required parameter does not exist;
- the parameter is read-only; or
- the parameter cannot currently be modified.

!!! warning "Missing project parameter?"

    If a required parameter is missing, do not create a replacement parameter
    manually.

    Report the issue so that the project can be checked against the
    office-standard configuration.

This helps ensure that project parameters remain consistent between projects.

---

## Worksets Are Reported as Missing

Project Setup compares the current project worksets with the expected Flow
configuration.

If required worksets are missing, review the inspection results before creating
them.

➡️ **[Worksets](worksets.md)**

---

## Worksets Cannot Be Created

Worksets are only available in a workshared Revit project.

If the project is not currently workshared, Project Setup cannot complete the
workset configuration.

!!! note "Worksharing required"

    Enable Revit worksharing before attempting to create the required worksets.

    After worksharing has been enabled, refresh Project Setup to inspect the
    project again.

---

## Project Folders Are Reported as Missing

Project Setup checks configured project storage locations independently.

A folder may be reported as missing because:

- the project folder has not yet been created;
- the selected storage location is unavailable;
- the project information required for folder naming is incomplete; or
- the computer cannot currently access the configured location.

Review the folder target before creating any folders.

➡️ **[Project Folders](project-folders.md)**

---

## A Project Folder Location Is Unavailable

If a configured project location cannot be accessed, first confirm that the
location is available outside Revit.

For example, check that:

- the required network or project storage location is accessible;
- you have access to the location; and
- the location has not been disconnected or moved.

!!! warning "Don't create an alternative folder manually"

    If the configured project location is unavailable, resolve the connection
    or access problem before provisioning the project folders.

    Project Setup cannot create folders in a location that is unavailable to
    the current workstation.

---

## I Do Not Want to Create Folders in Every Location

Project folder targets can be selected individually.

Use the checkboxes in the Project Folders section to select only the locations
that should be processed.

Unselected locations will not be provisioned.

!!! tip "Check the selected targets"

    Before creating folders, review the selected locations and clear any
    target that is not required for the project.

---

## Project Setup Is Showing Old Information

Project Setup does not continuously re-inspect the project while you work.

If the Revit project or external project folders have changed since the last
inspection, use **Refresh** to run the inspection again.

This is particularly useful after:

- updating Project Information;
- creating worksets;
- creating project folders; or
- making relevant changes outside Project Setup.

---

## The Status Still Shows Incomplete After Making Changes

Run **Refresh** after completing the required setup action.

Project Setup will inspect the current state again and update the displayed
status.

If the item continues to show as incomplete, review the relevant setup section
to determine which requirement has not been satisfied.

---

## Something Does Not Look Right

If Project Setup reports unexpected information:

1. Do not repeatedly apply the same setup action.
2. Refresh the inspection.
3. Review the affected setup section.
4. Confirm the current state directly in Revit or the relevant project location.

!!! warning "Avoid repeatedly applying an action"

    If a setup action appears to have failed, do not repeatedly run it in an
    attempt to force the status to change.

    Refresh the inspection first and confirm the actual project state.

If the result still appears incorrect, report the issue to the Flow administrator.

Where possible, include:

- the Revit version;
- the project number or project name;
- the Project Setup section affected;
- what you expected to happen;
- what actually happened; and
- a screenshot of the Project Setup window.

---

## Related Help

- [Project Setup](index.md)
- [Creating a New Project](new-projects.md)
- [Reviewing a Current Project](current-projects.md)
- [Project Information](project-information.md)
- [Worksets](worksets.md)
- [Project Folders](project-folders.md)