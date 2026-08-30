# Project Setup Troubleshooting

Use this page to resolve common issues encountered while using **Project
Setup**.

------------------------------------------------------------------------

## Project Setup Will Not Open

1.  Confirm the **Flow** ribbon has loaded.
2.  Check whether other Flow tools open normally.
3.  Restart Revit.
4.  Try Project Setup again.

------------------------------------------------------------------------

## Project Identity Still Says Start Here

Check **Project Year**, **Project Number**, **Client** and **Location**,
then select **Review Identity**.

Editing an identity value after successful review deliberately clears
the review and returns the **Start here** cue.

➡️ **[Project Identity](project-identity.md)**

------------------------------------------------------------------------

## Create Project Is Disabled

Check for:

-   a valid reviewed Project Identity;
-   a selected Project Profile;
-   a successful template preflight; and
-   an available compatible Revit template.

➡️ **[Creating a New Project](new-projects.md)**

------------------------------------------------------------------------

## Project Profile or Template Is Not Available

Confirm the intended Revit version, selected Project Profile and
configured office template availability.

!!! warning "Don't substitute another template"

    Do not use an unrelated template simply to bypass Project Setup preflight.

------------------------------------------------------------------------

## Project Information Is Incomplete

Inspect the project, review current and proposed Project Information
values, apply the intended changes and re-inspect where required.

➡️ **[Project Information](project-information.md)**

------------------------------------------------------------------------

## A Project Information Field Cannot Be Changed

The required parameter may be missing, read-only or otherwise
unavailable.

Do not create an ad-hoc replacement parameter merely to clear the
status.

------------------------------------------------------------------------

## Worksharing Is Not Enabled

If worksharing is appropriate, use **Enable Worksharing** in Project
Setup and then inspect the project again as required.

➡️ **[Worksharing](worksharing.md)**

------------------------------------------------------------------------

## Worksets Are Missing or Cannot Be Configured

Review the Worksets inspection.

Workset configuration requires a workshared project, so complete
Worksharing first where necessary.

➡️ **[Worksets](worksets.md)**

------------------------------------------------------------------------

## Project Folders Cannot Be Inspected or Created

Confirm that Project Identity has been reviewed and that configured
target locations are accessible.

A target may also require attention because its expected location or
template structure is unavailable, incomplete or conflicts with the
proposed plan.

➡️ **[Project Folders](project-folders.md)**

------------------------------------------------------------------------

## I Do Not Want to Create Folders in Every Location

Clear the checkbox for any target that should not be provisioned. Only
selected targets are processed.

------------------------------------------------------------------------

## Existing Building Shows Attention Required

The cleanup inspection found direct cleanup targets.

Open **Review / Prepare** and review the Cleanup card before taking
action.

➡️ **[Existing Building](existing-building.md)**

------------------------------------------------------------------------

## Clean Up Is Disabled

**Clean Up** is available only when direct cleanup targets have been
identified.

If reinspection reports no remaining targets, the disabled button is
expected.

------------------------------------------------------------------------

## Revit Displays a Deletion Warning During Clean Up

Cleanup uses Revit's normal deletion system.

Revit may display a native warning or error for hosted, inserted, infill
or dependent relationships. Review the Revit message carefully.

------------------------------------------------------------------------

## More Elements Were Deleted Than the Cleanup Count

The Cleanup count reports direct targets identified by Flow.

Revit can also delete dependent elements, so the final deletion count
can be greater.

------------------------------------------------------------------------

## Apply Phasing Is Disabled

Run **Inspect** in the Phasing card.

Apply Phasing requires a resolved Existing phase and at least one
writable candidate outside Existing.

If no actionable elements remain, the disabled button is expected.

------------------------------------------------------------------------

## Some Phasing Candidates Are Read-Only

Some elements expose `Phase Created` but do not allow Flow to write it
directly.

These are reported as read-only and are not directly modified by Flow.

------------------------------------------------------------------------

## The Number Updated by Flow Does Not Match the Final Phase Change

This can be expected.

**Directly updated by Flow** counts explicit Flow changes. Revit may
propagate phasing to related or dependent elements. Reinspection reports
the resulting model state.

------------------------------------------------------------------------

## An Element Still Remains Outside Existing

A remaining non-Existing element may be read-only or controlled by
Revit.

If no writable non-target elements remain and **Apply Phasing** is
disabled, Flow has no further actionable phasing changes from that
inspection.

------------------------------------------------------------------------

## Project Setup Is Showing Old Information

Use **Refresh** after relevant changes made outside Project Setup.

Some workflows, including Existing Building Cleanup and Phasing,
automatically re-inspect their own state after execution.

------------------------------------------------------------------------

## Something Does Not Look Right

1.  Do not repeatedly apply the same setup action.
2.  Re-inspect or refresh.
3.  Review the reported summary.
4.  Confirm the actual state in Revit or the relevant external location.

If the result remains unexpected, report the Revit version, project,
affected Project Setup section, expected result, actual result and a
screenshot.

------------------------------------------------------------------------

## Related Help

-   [Project Setup](index.md)
-   [Project Identity](project-identity.md)
-   [Creating a New Project](new-projects.md)
-   [Reviewing a Current Project](current-projects.md)
-   [Project Information](project-information.md)
-   [Project Folders](project-folders.md)
-   [Worksharing](worksharing.md)
-   [Worksets](worksets.md)
-   [Existing Building](existing-building.md)
