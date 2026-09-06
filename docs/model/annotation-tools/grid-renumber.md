# Grid Renumber

**Grid Renumber** renumbers Revit grids sequentially in the order they are selected.

Use it when an existing grid sequence needs to be reorganised quickly without manually editing each grid name.

------------------------------------------------------------------------

## Opening the Tool

On the **Flow** ribbon:

1.  Open **Annotation**.
2.  Choose **Grid Renumber**.

------------------------------------------------------------------------

## Renumbering Grids

1.  Start **Grid Renumber**.
2.  Enter the starting grid number.
3.  Select the first grid.
4.  Continue selecting grids in the required numbering order.
5.  Press **Esc** when finished.
6.  Review the completed grid sequence.

!!! tip "Selection order controls numbering"

    Pick grids in the exact order you want the new numbers to be assigned.

------------------------------------------------------------------------

## Existing Number Conflicts

The verified source workflow handles an existing grid using a requested number by moving the conflicting grid forward to the next available value.

This allows a new numbering sequence to be applied without first clearing every existing grid name manually.

------------------------------------------------------------------------

## Visual Feedback

The source workflow temporarily marks grids as they are processed using view overrides.

Those overrides are removed when the operation finishes.

------------------------------------------------------------------------

## Invalid Selections

Only Revit grids can be renumbered.

If another element type is selected, the source workflow ignores the pick and asks for another grid.

------------------------------------------------------------------------

## Finishing the Workflow

Press **Esc** to finish.

The completed numbering changes are retained.

------------------------------------------------------------------------

## Related Help

-   [Grid Renumber Troubleshooting](troubleshooting.md)
-   [Renumber](renumber.md)
-   [Annotation](index.md)