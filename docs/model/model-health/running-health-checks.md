# Running Health Checks

Model Health audits the active Revit project using all currently
available health checks.

The checks run together. Individual checks cannot currently be enabled,
disabled or run separately.

------------------------------------------------------------------------

## Open Model Health

On the Revit ribbon:

**Flow → Model → Health**

The Model Health window opens and **the audit starts automatically**.

There is no need to click **Run Audit** for the initial review.

------------------------------------------------------------------------

## Step 1 --- Wait for the Automatic Audit

Flow runs each registered check against the active project and then
updates the dashboard and results grid.

The current checks run in the following order:

1.  Revit Warnings
2.  Imported CAD
3.  In-Place Families
4.  Unplaced Rooms
5.  Model Groups
6.  Duplicate Marks

!!! note "Point-in-time results"

    The dashboard represents the project when the most recent audit was run.

    Model Health does not continuously monitor the project while you work.

------------------------------------------------------------------------

## Step 2 --- Review the Dashboard

The summary cards show:

### Model Health

The overall health score and rating.

The score is based on the number and severity of active issues.
Higher-severity issues have a greater effect.

### Audit Checks

The total number of checks executed.

### Passed

The number of checks with no active issues.

### Needs Attention

The number of checks containing one or more active issues.

### Issues Found

The total number of active issues, together with the number of:

-   Critical
-   High
-   Medium
-   Low

severity issues.

<!-- SCREENSHOT: Main results grid with a Failed row selected.
Include the metric cards and clearly show Check, Category, Severity, Status,
Issues and Duration, with Review Issues visible. -->

------------------------------------------------------------------------

## Step 3 --- Review the Audit Results

Each audit check appears as a row in the results grid.

The grid shows:

-   **Check**
-   **Category**
-   **Severity**
-   **Status**
-   **Issues**
-   **Duration**

A check with no active issues is shown as **Passed**.

A check containing one or more active issues is shown as **Failed**.

Select a Failed row and click **Review Issues** to investigate it. You
can also double-click a result containing issues to open its Issue
Details window.

See [**Reviewing Issues**](reviewing-issues.md).

------------------------------------------------------------------------

## What the Current Checks Evaluate

### Revit Warnings

Reads the warnings currently reported by Revit.

Each Revit warning is reported as a separate **High** severity Model
Health issue. Where Revit provides affected elements, those elements can
be reviewed from Model Health.

### Imported CAD

Reviews CAD `ImportInstance` content in the project, including both
imported and linked CAD.

Instances are grouped by their CAD category/name.

-   **Imported CAD** is reported at **High** severity.
-   A group containing only **Linked CAD** instances is reported at
    **Low** severity so that the ongoing need for the link can be
    reviewed.

!!! note "CAD links are included"

    A CAD link appearing in this check does not mean that Flow considers it equivalent to an imported CAD file.

    Linked CAD is reported at a lower severity and is included so its continued use can be reviewed.

### In-Place Families

Identifies family instances belonging to Revit in-place families.

Instances are grouped by family, with one **Medium** severity issue for
each in-place family found.

The check does not automatically determine that an in-place family is
incorrect. It identifies it for review.

### Unplaced Rooms

Identifies Room elements whose Revit `Location` is currently null.

Each unplaced room is reported as a separate **Medium** severity issue.

!!! note "What this check does not cover"

    This check is specifically for unplaced rooms. It does not currently audit placed rooms for enclosure, area or other room-quality conditions.

### Model Groups

Identifies model groups currently used in the project.

Instances are grouped by group type, with one **Medium** severity issue
for each group type found.

The check is intended to prompt review of whether the group is still
required and is being used consistently. It does not automatically
determine that a model group is incorrect.

### Duplicate Marks

Identifies duplicate non-blank **Mark** values within supported Revit
categories.

The currently supported categories are:

-   Doors
-   Windows
-   Rooms
-   Mechanical Equipment
-   Plumbing Fixtures
-   Generic Models
-   Speciality Equipment
-   Casework
-   Furniture

Duplicate Marks is reported at **High** severity.

Marks are compared **within the same category**. For example, a Door and
a Window may have the same Mark without being treated as a duplicate by
this check.

Blank Marks are ignored.

------------------------------------------------------------------------

## Ignored Issues and the Audit

Issues that have been intentionally ignored are filtered out before the
active dashboard is presented.

This means ignored issues do not contribute to:

-   the active issue count;
-   the Passed / Needs Attention result after filtering; or
-   the displayed Model Health score.

Ignored issues are stored locally for the current Windows user and
project rather than inside the Revit model.

See [**Reviewing Issues**](reviewing-issues.md) for how to ignore and
restore issues.

------------------------------------------------------------------------

## Run the Audit Again

Use **Run Audit** after making changes to the Revit model.

Flow reruns all six checks and replaces the displayed results with a new
assessment of the current project.

You do not need to rerun manually after ignoring issues or after closing
the **Ignored Issues** window; those workflows automatically trigger a
new audit.

!!! tip "Re-run after correcting the model"

    If you fix an issue directly in Revit, use **Run Audit** before relying on the displayed score or issue counts.

------------------------------------------------------------------------

## Current Limitations

Model Health is currently an audit and review tool.

-   Checks run as a complete set rather than individually.
-   Results are point-in-time rather than live.
-   Model Health does not currently auto-fix the conditions reported by
    these checks.
-   Some checks intentionally identify conditions for review rather than
    determining that the condition is always incorrect.
-   Ignored issues are user-local and are not shared through the Revit
    project.

------------------------------------------------------------------------

## Related Help

-   [Model Health](index.md)
-   [Reviewing Issues](reviewing-issues.md)
-   [Troubleshooting](troubleshooting.md)