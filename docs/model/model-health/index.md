# Model Health

**Model Health** audits the current Revit project for common
model-quality conditions and presents the results through a coordinated
health dashboard.

Use it to assess overall model health, review individual audit checks,
investigate affected elements and manage issues that have been
intentionally ignored.

------------------------------------------------------------------------

## Open Model Health

On the Revit ribbon:

**Flow → Model → Health**

When Model Health opens, **Flow automatically runs the complete audit**
against the active project. You do not need to start the first audit
manually.

!!! info "The audit runs automatically"

    All currently available Model Health checks run when the window opens.

    Use **Run Audit** later to refresh the results after making changes to the model.

------------------------------------------------------------------------

## How Model Health Works

For a first-time review:

1.  Open **Flow → Model → Health**.
2.  Wait for the automatic audit to complete.
3.  Review the dashboard and the audit results.
4.  Select a check showing **Failed** and click **Review Issues**.
5.  Review an individual issue and use **Select Elements** to
    investigate the affected Revit elements.
6.  Correct the condition in Revit, or ignore it if it has been reviewed
    and intentionally accepted.
7.  Use **Run Audit** after model changes to refresh the results.

<!-- SCREENSHOT: Main Model Health window after the automatic audit.
Show all five metric cards, at least one Passed result, at least one Failed result,
the audit results grid and the footer actions. -->

------------------------------------------------------------------------

## Dashboard

After the audit completes, the summary cards provide a quick overview of
the current active results.

-   **Model Health** --- the calculated health score and rating.
-   **Audit Checks** --- the number of checks executed.
-   **Passed** --- checks where no active issues were identified.
-   **Needs Attention** --- checks containing one or more active issues.
-   **Issues Found** --- the total active issue count, together with a
    severity breakdown.

The results grid below the dashboard shows the outcome of each
individual check.

!!! note "Ignored issues"

    Issues that you intentionally ignore are excluded from the active audit results and from the displayed Model Health score.

    Ignored issues are stored locally for the current Windows user and project. They are not written into the Revit model and are not automatically shared with other users.

------------------------------------------------------------------------

## Health Score

The **Model Health** score provides a high-level indication of the
conditions identified by the current audit.

The score starts from a healthy-model baseline and is reduced according
to the number and severity of active issues. Higher-severity issues have
a greater effect on the score.

The current health ratings are:

  Score     Rating
  --------- -----------
  95--100   Excellent
  85--94    Good
  70--84    Fair
  50--69    Poor
  0--49     Critical

!!! note "A model-health indicator"

    The Model Health score is a Flow model-quality indicator.

    It is not a Revit performance score or a formal project-compliance assessment.

------------------------------------------------------------------------

## Current Audit Checks

The current audit includes:

-   Revit Warnings
-   Imported CAD
-   In-Place Families
-   Unplaced Rooms
-   Model Groups
-   Duplicate Marks

For details about what each check evaluates, see [**Running Health
Checks**](running-health-checks.md).

------------------------------------------------------------------------

## What Do You Want to Do?

### Understand or Refresh the Audit

Learn what each check evaluates, how to interpret the dashboard and when
to use **Run Audit**.

➡️ [**Running Health Checks**](running-health-checks.md)

### Review Identified Issues

Investigate affected Revit elements, ignore accepted conditions, restore
ignored issues and remove Model Health's temporary isolation.

➡️ [**Reviewing Issues**](reviewing-issues.md)

### Having Problems?

Find help if the audit does not complete, a command appears to do
nothing, an element is difficult to locate or the displayed results are
no longer current.

➡️ [**Troubleshooting**](troubleshooting.md)

------------------------------------------------------------------------

## Getting Help

Hover over **Health** on the Flow ribbon and press **F1** to return
directly to Model Health help.