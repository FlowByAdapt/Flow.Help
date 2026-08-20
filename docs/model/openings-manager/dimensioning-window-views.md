# Dimensioning Window Views

Use **Dimension Window Views** to create or regenerate the standard
dimensions on component window elevations.

The command can process the active window view or all recognised window
views.

------------------------------------------------------------------------

## Choose the Scope

Run **Dimension Window Views** and choose:

-   **Active Window View**
-   **All Window Views**

Use **Active Window View** when working on one elevation.

Use **All Window Views** to batch-process the recognised window
elevations.

------------------------------------------------------------------------

## Which Views Are Processed?

For batch dimensioning, Flow looks for section views using the standard
New window naming pattern:

``` text
W##
```

For example:

``` text
W01
W02
W03
```

Existing `Wx##` views are not included in the batch operation.

------------------------------------------------------------------------

## Curtain Wall Views

Curtain wall elevations also use `W##` marks, so they may be encountered
during the batch scan.

Flow checks whether the view contains a genuine Revit Window family
instance.

If no Window family instance can be resolved, the view is skipped and
can be reported as:

``` text
No window found (likely curtain wall view)
```

This is an expected skip rather than a failed curtain wall dimensioning
operation.

!!! info "Curtain walls are not dimensioned by this command"

    Dimension Window Views is designed for component Window families.

    Curtain wall elevations can share the same W-style view naming convention, but they are not dimensioned by this workflow.

------------------------------------------------------------------------

## Required Family References

To create the complete standard dimension set, Flow looks for named
references in the Window family:

-   **Left**
-   **Right**
-   **Sill**
-   **Head**
-   **FFL**

These references allow Flow to build the required dimension strings
consistently.

------------------------------------------------------------------------

## Dimensions Created

When the required references are available, Flow creates:

-   Width
-   Height
-   Sill
-   Overall Height

If a usable **FFL** reference is not available, Flow can still create
the Width and Height dimensions.

------------------------------------------------------------------------

## Existing Dimensions

Before creating the standard dimensions, Flow removes the existing
dimensions from the opening view.

The command therefore acts as a **regenerate dimensions** operation
rather than simply adding another set of dimensions.

!!! warning "Existing dimensions are replaced"

    Dimension Window Views removes the existing dimensions in the processed window elevation before creating the Flow standard dimensions.

    Review manually customised dimensions before running the command.

------------------------------------------------------------------------

## Missing References

If the Window family does not provide the required Left/Right or
Sill/Head references, Flow cannot create the standard dimension set.

If a requested dimension fails during creation, the operation for that
view is rolled back rather than leaving a partially regenerated
dimension set.

------------------------------------------------------------------------

## Batch Results

When processing all window views, the completion summary can report:

-   Views Checked
-   Dimensioned
-   Skipped
-   Failed

Skipped curtain wall candidates and genuine dimensioning failures are
reported separately where applicable.

------------------------------------------------------------------------

## Recommended Workflow

For a new set of window elevations:

1.  Standardise the opening marks.
2.  Generate the opening views.
3.  Conform the views if required.
4.  Run **Dimension Window Views**.
5.  Review the resulting dimensions.
6.  Place the views on the opening sheets.

------------------------------------------------------------------------

## If a Window View Is Skipped

Check that:

-   the view follows the expected `W##` naming convention
-   the view represents a component Window rather than a curtain wall
-   the Window family provides the required named references
-   the opening can be resolved from the current view

For further checks:

➡️ [**Openings Manager Troubleshooting**](troubleshooting.md)

------------------------------------------------------------------------

## Related Help

-   [**Opening Views**](opening-views.md)
-   [**Generating Opening Views**](generating-opening-views.md)
-   [**Conforming Opening Views**](conforming-opening-views.md)
-   [**Placing Opening Views on Sheets**](placing-views-on-sheets.md)