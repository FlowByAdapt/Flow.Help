# Grid Dimensions

**Grid Dimensions** creates continuous dimension strings for selected grids in the active view.

The workflow groups parallel grids and places a coordinated dimension chain using a selected Revit dimension type and offset.

------------------------------------------------------------------------

## Opening the Tool

On the **Flow** ribbon:

1.  Open **Annotation**.
2.  Choose **Grid Dimensions**.

------------------------------------------------------------------------

## Supported Views

The source workflow supports:

-   Floor Plans
-   Reflected Ceiling Plans
-   Engineering Plans
-   Area Plans
-   Sections
-   Elevations
-   Detail Views

------------------------------------------------------------------------

## Creating Grid Dimensions

1.  Open the required Revit view.
2.  Start **Grid Dimensions**.
3.  Choose the required linear **Dimension Type**.
4.  Enter the dimension offset.
5.  Choose the grid orientation:
    -   **Vertical**
    -   **Horizontal**
    -   **Angled**
6.  Select the grids to dimension.
7.  Complete the Revit selection.

Flow filters the selection, groups parallel grids and creates a continuous dimension string for each usable group.

The workflow can then be repeated for another orientation or grid group.

------------------------------------------------------------------------

## Dimension Type

Grid Dimensions uses a linear Revit Dimension Type selected at the start of the workflow.

The historical workflow places **ADa_Blue** first in the chooser when that type exists, but other linear Dimension Types can be selected.

------------------------------------------------------------------------

## Dimension Offset

The source workflow uses an offset entered in millimetres.

The default is **350 mm**. Invalid or non-positive values fall back to the default.

------------------------------------------------------------------------

## How Grids Are Filtered

Only grids matching the selected orientation are used.

The source workflow also ignores grids that are already referenced by an existing dimension in the active view.

At least two usable grids are required to create a dimension string.

!!! info "Mixed selections are filtered"

    You can select grids that do not match the chosen orientation; unsupported selections are ignored rather than used in the dimension chain.

------------------------------------------------------------------------

## Dimension Placement

For vertical grid sets, the dimension is placed above the selected grids.

For horizontal grid sets, the dimension is placed to the left.

Angled grid sets are dimensioned using the grid direction and a perpendicular dimension direction.

------------------------------------------------------------------------

## Related Help

-   [Grid Dimensions Troubleshooting](troubleshooting.md)
-   [Annotation](index.md)
-   [Wall Dimensions](wall-dimensions.md)
-   [Join Dimensions](join-dimensions.md)