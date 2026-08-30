# Project Folders

Project Folders checks configured project storage targets and can create
the standard folder structure required for a Flow project.

Multiple configured locations can be inspected and provisioned
independently.

------------------------------------------------------------------------

## Before You Begin

Project Folder planning depends on a reviewed **Project Identity**.

Confirm the identity and select **Review Identity** before planning
folders.

➡️ **[Project Identity →](project-identity.md)**

------------------------------------------------------------------------

## Inspect Folders

Flow checks configured target locations and determines the state of each
target.

Project Setup distinguishes locations that already contain the expected
project folder, are available for creation, or require attention.

------------------------------------------------------------------------

## Selecting Targets

Use the target checkboxes to choose which locations should be included.

Only selected targets are considered for provisioning.

!!! tip "Only create the locations you need"

    Clear any target that should not be provisioned for the project.

------------------------------------------------------------------------

## Folder Plan

The proposed folder name and locations are derived from the reviewed
Project Identity and configured folder rules.

If an identity value changes, review the identity again before relying
on the previous folder plan.

------------------------------------------------------------------------

## Creating Project Folders

When selected targets have been inspected and are available, use
**Create Project Folders**.

Existing exact project folders are recognised and are not recreated
simply because the workflow is run again.

------------------------------------------------------------------------

## Targets Requiring Attention

A target may require attention if the expected location or template
structure is unavailable, incomplete or conflicts with the proposed
plan.

Where Project Setup offers its supported recovery workflow for
incomplete provisioning, use that workflow rather than manually forcing
the folder state.

------------------------------------------------------------------------

## Re-inspection

After provisioning, Project Setup refreshes the folder plan so the
resulting state can be reviewed.

Use **Refresh** when a relevant folder has been changed outside the
current workflow.

------------------------------------------------------------------------

## Related Help

-   [Project Setup](index.md)
-   [Project Identity](project-identity.md)
-   [Reviewing a Current Project](current-projects.md)
-   [Project Information](project-information.md)
-   [Worksets](worksets.md)
-   [Troubleshooting](troubleshooting.md)
