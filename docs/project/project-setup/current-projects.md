# Reviewing a Current Project

Project Setup can inspect the active Revit project and bring supported
setup tasks together in one coordinated workflow.

The Current Project area reports what has already been completed, what
is ready to continue and what requires attention.

------------------------------------------------------------------------

## Opening the Current Project Workflow

Open the Revit project that you want to review, then go to:

**Flow → Project → Setup**

------------------------------------------------------------------------

## Inspect Project

Select **Inspect Project** to inspect the supported Current Project
setup areas.

Inspection is read-only. It reports the current state without
automatically modifying the Revit project.

!!! info "Inspect first"

    Review the reported state before choosing an action that changes the project.

------------------------------------------------------------------------

## Setup Overview

The Current Project dashboard combines supported inspection areas into
an overall setup overview.

Statuses can include **Complete**, **Ready**, **Attention Required**,
**Not Inspected**, **Not Applicable** and **Failed**.

Each area also provides its own summary.

------------------------------------------------------------------------

## Project Information

Inspect supported project metadata stored in the active Revit project
and review or edit values where required.

➡️ **[Project Information →](project-information.md)**

------------------------------------------------------------------------

## Project Folders

Inspect configured project-folder targets using the reviewed Project
Identity. Target locations can be selected independently before
provisioning.

➡️ **[Project Folders →](project-folders.md)**

------------------------------------------------------------------------

## Worksharing

Project Setup reports whether the active project is workshared and can
enable worksharing when the action is available.

➡️ **[Worksharing →](worksharing.md)**

------------------------------------------------------------------------

## Worksets

For a workshared project, Project Setup compares the current worksets
with the expected Flow worksets and can create missing required
worksets.

➡️ **[Worksets →](worksets.md)**

------------------------------------------------------------------------

## Existing Building

The Existing Building area inspects the active project for cleanup
content that may need attention before preparing an Existing Building
model.

The review contains two separate operations:

1.  **Cleanup** --- removes identified demolished elements, rooms and
    room separation lines.
2.  **Phasing** --- inspects `Phase Created` and can apply the Existing
    phase to applicable writable elements.

Neither operation is performed merely by opening the review window.

➡️ **[Existing Building →](existing-building.md)**

------------------------------------------------------------------------

## Refreshing the Inspection

Use **Refresh** when changes have been made outside Project Setup or the
active Revit context has changed.

Some actions automatically re-inspect their own workflow after
execution.

------------------------------------------------------------------------

## Related Help

-   [Project Setup](index.md)
-   [Project Identity](project-identity.md)
-   [Creating a New Project](new-projects.md)
-   [Project Information](project-information.md)
-   [Project Folders](project-folders.md)
-   [Worksharing](worksharing.md)
-   [Worksets](worksets.md)
-   [Existing Building](existing-building.md)
-   [Troubleshooting](troubleshooting.md)
