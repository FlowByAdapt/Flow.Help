# Reviewing Global Parameters

Use the **Opening GP Dashboard** to review the Global Parameters
included in the current Flow opening workflow.

------------------------------------------------------------------------

## Open the Dashboard

Open:

**Flow → Content → Parameters Manager**

The dashboard scans the current model automatically when Parameters
Manager opens.

Use **Refresh Dashboard** after making changes if you want to rescan the
model.

------------------------------------------------------------------------

## Dashboard Summary

The three summary cards provide quick filters.

### Total GPs

Shows all Global Parameters included in the Opening GP Dashboard.

### Associated

Shows Global Parameters with one or more associations detected by the
dashboard scan.

### Unused

Shows Global Parameters with no associations detected by the dashboard
scan.

Select a card to filter the grid.

!!! note "Dashboard scope"

    The Opening GP Dashboard deliberately excludes some office graphics and project-control Global Parameters that are outside the opening workflow.

    **Total GPs** therefore does not represent every Global Parameter stored in the Revit model.

------------------------------------------------------------------------

## Review the Grid

The dashboard grid shows:

  -----------------------------------------------------------------------
  Column                              Description
  ----------------------------------- -----------------------------------
  **GP Name**                         Global Parameter name.

  **Type**                            Value type reported by Flow.

  **Current Value**                   Current value of the Global
                                      Parameter.

  **Associations**                    Number of associations detected by
                                      the dashboard scan.

  **Status**                          **Associated** or **Unused**.
  -----------------------------------------------------------------------

Supported type descriptions include **Text**, **Length / Number**,
**Integer / Yes-No**, and **Element**.

Some Current Value cells are editable.

➡️ [**Editing Global Parameter
Values**](editing-global-parameter-values.md)

------------------------------------------------------------------------

## Refresh the Dashboard

Select:

**Audit → Refresh Dashboard**

Use this after changing associations, importing Global Parameters, or
completing another workflow that affects the dashboard.

------------------------------------------------------------------------

## Related Help

-   [Parameters Manager](index.md)
-   [Editing Global Parameter
    Values](editing-global-parameter-values.md)
-   [Reviewing Associations](reviewing-associations.md)
-   [Auditing Global Parameters](auditing-global-parameters.md)
-   [Troubleshooting](troubleshooting.md)