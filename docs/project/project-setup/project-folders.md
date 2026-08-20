# Project Folders

The Project Folders section checks and creates the standard folder
structures required for a Flow project.

Multiple project storage locations can be reviewed and provisioned
independently.

---

## Opening Project Folders

Open:

**Flow → Project → Setup**

Open the **Project Folders** section.

---

## Folder Inspection

Flow checks the configured project folder locations and determines the
current state of each target.

This allows Project Setup to distinguish between folders that already exist
and folders that still need to be created.

---

## Target Locations

Each configured project folder location is shown separately.

This allows different project storage locations to be inspected and
provisioned independently.

Examples may include office project storage and other configured project
locations.

---

## Selecting Locations

Use the checkboxes beside the folder targets to choose which locations
should be included.

Only the selected locations are processed.

This allows a project folder to be created in one location without
automatically creating it in every configured location.

!!! tip "Only create the locations you need"

    Review the selected folder locations before applying the changes.

    Clear the checkbox for any location that you do not want Project Setup
    to provision.

---

## Creating Project Folders

After reviewing the proposed folder locations, apply the Project Setup
changes.

Flow creates the required project folder structure at the selected
locations.

Existing project folders are identified during inspection so that the
current state can be reviewed before changes are made.

!!! note "Existing folders are preserved"

    Project Setup checks the required folder structure before creating anything.

    Existing project folders are not recreated simply because you run the
    check again.

---

## Folder Naming

Project folder information is derived from the project identity entered
through Project Setup.

Ensure the project information is correct before creating project folders.

!!! warning "Check the project information first"

    Confirm the project number, project name and other required project
    information before creating folders.

    This information is used to determine the project folder location and naming.

See:

➡️ **[Project Information](project-information.md)**

---

## Refreshing the Results

After folders have been created, use **Refresh** to run the Project Setup
inspection again.

The newly created locations should then be reported as complete.

!!! tip "Folder created outside Flow?"

    Use **Refresh** if a project folder has been created or changed outside
    Project Setup.

    This updates the inspection results to reflect the current folder structure.

---

## Related Help

- [Project Setup](index.md)
- [Reviewing a Current Project](current-projects.md)
- [Project Information](project-information.md)
- [Worksets](worksets.md)
- [Troubleshooting](troubleshooting.md)