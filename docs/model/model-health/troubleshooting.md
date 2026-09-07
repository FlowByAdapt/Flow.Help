# Model Health Troubleshooting

Use the following checks if Model Health does not complete an audit, an
action appears to do nothing or the displayed results do not match what
you expect.

------------------------------------------------------------------------

## Model Health Does Not Complete the Initial Audit

The complete audit runs automatically when Model Health opens.

If the window does not complete its initial audit:

1.  Confirm that an active Revit project is open.
2.  Allow the current Revit operation to finish.
3.  Close and reopen Model Health.
4.  If the problem repeats, note which project and Revit version are
    affected.

The current audit runs all registered checks as a single sequence. A
problem encountered while executing a check may prevent the complete
audit from finishing.

------------------------------------------------------------------------

## A Check Shows Passed When I Expected Issues

A **Passed** result means that the current active audit did not identify
an issue for that check.

First:

1.  Confirm that the expected condition still exists.
2.  Click **Run Audit** to refresh the results.
3.  Check what that particular audit actually evaluates.

Some checks intentionally have a narrow scope.

For example:

-   **Unplaced Rooms** checks rooms with no placement location; it does
    not currently check placed rooms for enclosure or area.
-   **Duplicate Marks** checks supported categories only and compares
    Marks within the same category.
-   **Model Groups** reports group types that exist; it does not apply a
    separate rule to decide whether each group is incorrectly used.

------------------------------------------------------------------------

## Review Issues Does Nothing

**Review Issues** requires a selected result containing one or more
active issues.

Check that:

1.  the selected result shows **Failed**; and
2.  its **Issues** value is greater than zero.

You can also double-click a result containing issues to open its Issue
Details window.

------------------------------------------------------------------------

## Select Elements Does Nothing

**Select Elements** works on the individual issue row.

You do **not** need to tick the issue checkbox first.

If nothing appears to happen:

1.  confirm that the issue reports affected elements;
2.  confirm that those elements still exist in the project;
3.  return to Model Health and click **Run Audit** if the model has
    changed; and
4.  reopen **Review Issues** and try again.

If Revit does not accept the external selection request, Flow displays a
**Flow Model Health** message containing the Revit request status.

------------------------------------------------------------------------

## The Elements Are Selected but I Cannot See Them as Expected

Model Health normally tries to review affected elements in:

**3D-01-Work Main**

For issues containing a Property Line, it instead looks for:

**SITE-01-Site Plan**

or, if that exact view is unavailable, another non-template plan view
with `site` in its name.

If the preferred review view cannot be found, Flow remains in the
current active view.

Visibility can therefore still be affected by the current view and
normal Revit visibility conditions.

------------------------------------------------------------------------

## My Existing Temporary Hide/Isolate State Disappeared

Model Health uses Revit Temporary Hide/Isolate to focus on affected
elements.

Before applying its own isolation, it clears any existing Temporary
Hide/Isolate state in the target review view.

If you had already created a temporary isolation state in that view, it
is not preserved by the Model Health review workflow.

------------------------------------------------------------------------

## Ignore Selected Does Nothing

**Ignore Selected** uses the issue checkboxes.

Before clicking it:

1.  tick at least one issue in the Issue Details window; and
2.  click **Ignore Selected**.

If no issue is ticked, the command intentionally makes no change.

------------------------------------------------------------------------

## An Issue Disappeared After I Ignored It

This is expected.

Ignored issues are filtered out of the active audit results and do not
contribute to the displayed Model Health score.

Open **Ignored Issues** from the main Model Health window to review or
restore them.

!!! note "Ignored issues are user-local"

    Ignored issues are stored locally for the current Windows user and project.

    Another user opening the same Revit project will not automatically inherit your ignored list.

------------------------------------------------------------------------

## Restore Selected Does Nothing

In the **Ignored Issues** window, tick at least one ignored item before
clicking **Restore Selected**.

Alternatively, use **Restore All** to restore every ignored issue.

When the Ignored Issues window closes, Model Health automatically runs
the audit again.

A restored issue will only reappear if the underlying model condition
still exists.

------------------------------------------------------------------------

## My Health Score Changed After Ignoring an Issue

This is expected.

Ignored issues are excluded before the active Model Health score is
calculated.

Ignoring an issue can therefore increase the displayed score even though
the underlying Revit model condition has not changed.

Use Ignore only for conditions that have been reviewed and intentionally
accepted.

------------------------------------------------------------------------

## My Health Score Did Not Change After Fixing the Model

Model Health results are point-in-time.

After correcting a model condition:

1.  return to Model Health;
2.  click **Run Audit**; and
3.  review the updated dashboard and result grid.

The displayed score does not continuously recalculate while you edit the
model.

------------------------------------------------------------------------

## Restore View Does Not Return Me to My Previous View

This is expected with the current implementation.

**Restore View** removes Temporary Hide/Isolate from the currently
active Revit view.

It does not:

-   reactivate the view that was open before issue review;
-   restore the previous zoom position;
-   restore the previous Revit selection; or
-   recreate a previous Temporary Hide/Isolate state.

Closing Model Health also requests removal of temporary isolation from
the currently active view.

------------------------------------------------------------------------

## Results Are Out of Date

If the model has changed since the last audit:

1.  return to Model Health;
2.  click **Run Audit**; and
3.  wait for the refreshed results.

You do not need to manually rerun after **Ignore Selected** or after
closing **Ignored Issues**, because those workflows trigger a new audit
automatically.

------------------------------------------------------------------------

## A Check Takes Longer Than Expected

The **Duration** column shows how long each audit check took to execute.

Different checks inspect different quantities of Revit data, so their
execution times may vary with project size and content.

A longer duration does not by itself mean that the check has failed.

------------------------------------------------------------------------

## Reporting a Problem

If a problem continues, record:

-   the Revit version;
-   the project involved;
-   the audit check involved;
-   what you expected to happen;
-   what happened instead;
-   any message displayed by Flow; and
-   a screenshot where useful.

------------------------------------------------------------------------

## Related Help

-   [Model Health](index.md)
-   [Running Health Checks](running-health-checks.md)
-   [Reviewing Issues](reviewing-issues.md)