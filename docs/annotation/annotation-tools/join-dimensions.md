# Join Dimensions

**Join Dimensions** combines two or more compatible dimension strings into one continuous dimension.

Flow collects the references from the selected dimensions, removes duplicates, orders the references along the dimension direction and recreates the dimension as a single string.

Supported dimension-segment labels are preserved where they can be matched to the recreated segments.

------------------------------------------------------------------------

## Opening the Tool

On the **Flow** ribbon:

1.  Open **Annotation**.
2.  Choose **Join Dimensions**.

------------------------------------------------------------------------

## Joining Dimension Strings

1.  Start **Join Dimensions**.
2.  Select two or more compatible dimensions that run in the same direction.
3.  Complete the selection.
4.  Flow validates the selected dimensions and creates a replacement continuous dimension.
5.  Continue selecting additional groups if required.
6.  Press **Esc** when finished.

!!! tip "Select dimensions with the same direction"

    Join Dimensions is intended for compatible dimension strings that describe the same dimension direction. Mixing unrelated or perpendicular strings will not produce a valid replacement dimension.

------------------------------------------------------------------------

## What Flow Preserves

Flow preserves the dimension references needed to recreate the combined string.

Where supported labels exist below dimension segments, Flow records those labels before recreating the dimension and reapplies them to matching segments afterwards.

This is particularly useful with labels created through **Dimension Labels**.

------------------------------------------------------------------------

## Staggered or Separated Dimension Strings

The workflow is designed to account for separated or staggered dimension strings rather than assuming all selected dimensions are perfectly coincident.

Flow orders the collected references along the replacement dimension direction before creating the new string.

------------------------------------------------------------------------

## Duplicate and Zero-Length Segments

Flow removes duplicate references and checks for references that would create zero-length dimension segments.

If necessary, unusable references are removed before the replacement dimension is accepted.

!!! info "Source dimensions are protected"

    The intended native workflow does not delete the original dimensions until a valid replacement dimension has been created successfully.

------------------------------------------------------------------------

## Finishing the Workflow

Press **Esc** to finish selecting dimension groups.

Cancelling the interactive selection should end the workflow cleanly rather than being treated as an error.

------------------------------------------------------------------------

## Related Help

-   [Join Dimensions Troubleshooting](troubleshooting.md)
-   [Annotation](index.md)
-   [Dimension Labels](dimension-labels.md)
-   [Wall Dimensions](wall-dimensions.md)
-   [Grid Dimensions](grid-dimensions.md)