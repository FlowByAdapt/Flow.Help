# Reviewing Model Health Issues

Use **Review Issues** to move from an audit result to the individual
conditions identified by that check.

Model Health can then help locate affected Revit elements, or allow an
accepted condition to be ignored.

------------------------------------------------------------------------

## Step 1 --- Select a Check Requiring Attention

In the main Model Health results grid, select a check showing:

**Status → Failed**

with an **Issues** count greater than zero.

Click:

**Review Issues**

You can also double-click a result containing issues.

The **Issue Details** window opens for that check.

------------------------------------------------------------------------

## Step 2 --- Review the Issue Details

Each issue row provides information about the condition identified by
the audit, including its title, suggested action and affected-element
count.

Depending on the check, one result may contain a single issue or several
separate issues.

<!-- SCREENSHOT: Issue Details window with several issue rows.
Show the checkboxes, issue information, affected-element count,
per-row Select Elements controls and Ignore Selected.
Caption should explain that Select Elements is per issue while
checkboxes are used for Ignore Selected. -->

------------------------------------------------------------------------

## Step 3 --- Investigate an Issue in Revit

To investigate one issue, click **Select Elements** on that issue's row.

**You do not need to tick the issue checkbox before using Select
Elements.**

Flow closes the Issue Details window and requests Revit to locate the
affected elements.

Where possible, Flow then:

1.  activates the preferred review view;
2.  removes any existing Temporary Hide/Isolate state in that target
    view;
3.  temporarily isolates the affected elements;
4.  selects them; and
5.  zooms to them.

This makes the elements identified by the audit easier to inspect in
context.

!!! important "Checkboxes have a different purpose"

    The checkboxes in Issue Details are used by **Ignore Selected**.

    They are not required for **Select Elements**, which acts on the individual issue row.

------------------------------------------------------------------------

## Preferred Review Views

For most affected elements, Model Health looks for the 3D view:

**3D-01-Work Main**

If the issue contains a Revit Property Line, Model Health instead looks
for:

**SITE-01-Site Plan**

If that exact site-plan view does not exist, Flow looks for a
non-template plan view with `site` in its name.

If the preferred review view cannot be found, Flow remains in the
current active view and continues the selection/isolation workflow
there.

!!! note "Temporary Hide/Isolate"

    Model Health uses Revit's Temporary Hide/Isolate mode to focus on the affected elements.

    If the target view already has a Temporary Hide/Isolate state, Model Health clears that state before applying its own temporary isolation.

------------------------------------------------------------------------

## Step 4 --- Correct the Condition

Review the selected elements and use the appropriate Revit tools to make
any required correction.

Examples may include:

-   resolving a Revit warning;
-   replacing imported CAD with a CAD link where practical;
-   reviewing an in-place family;
-   placing or deleting an unplaced room;
-   reviewing model-group usage; or
-   assigning unique Mark values.

Model Health does **not** currently auto-fix these conditions.

After making changes, return to Model Health and click **Run Audit** to
update the results.

------------------------------------------------------------------------

## Ignore an Accepted Issue

Some reported conditions may be intentional and acceptable for a
particular project.

To ignore one or more issues:

1.  Open **Review Issues**.
2.  Tick the checkbox beside each issue you want to ignore.
3.  Click **Ignore Selected**.

Flow stores the selected issues in the ignored list and **automatically
reruns the audit**.

The ignored issues are then removed from the active results and no
longer contribute to the displayed Model Health score.

!!! warning "Ignored does not mean resolved"

    Ignoring an issue does not modify the Revit model.

    Use Ignore only when the condition has been reviewed and intentionally accepted.

### Where ignored issues are stored

Ignored issues are stored locally for the current Windows user and
project.

They are **not written into the Revit model** and are not automatically
shared with another user opening the same project.

------------------------------------------------------------------------

## Review or Restore Ignored Issues

From the main Model Health window, click:

**Ignored Issues**

The Ignored Issues window shows the stored ignored conditions, including
their title, category and ignored date.

<!-- SCREENSHOT: Ignored Issues window with multiple items.
Show checkboxes, Title, Category, Ignored Date, Restore Selected and Restore All. -->

To return specific issues to the active audit:

1.  Tick the required ignored issues.
2.  Click **Restore Selected**.

To restore every ignored issue, use:

**Restore All**

When the Ignored Issues window closes, Model Health automatically runs
the audit again.

Restored conditions will reappear only if the current model still
satisfies the relevant check.

------------------------------------------------------------------------

## Restore the Review View

While reviewing affected elements, Model Health temporarily isolates
them in Revit.

Click:

**Restore View**

to remove the Temporary Hide/Isolate state from the currently active
Revit view.

Closing the Model Health window also requests the same removal
automatically.

!!! note "What Restore View does not restore"

    **Restore View** removes temporary isolation only.

    It does not switch back to a previously active view, restore a previous zoom position, restore the previous Revit selection or recreate a Temporary Hide/Isolate state that existed before Model Health review.

------------------------------------------------------------------------

## Typical Review Workflow

A typical issue-review cycle is:

**Failed Check → Review Issues → Select Elements → Review/Fix in Revit →
Run Audit**

For an accepted condition:

**Failed Check → Review Issues → Tick Issue → Ignore Selected →
Automatic Re-audit**

------------------------------------------------------------------------

## Related Help

-   [Model Health](index.md)
-   [Running Health Checks](running-health-checks.md)
-   [Troubleshooting](troubleshooting.md)