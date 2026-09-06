# Renumber

**Renumber** renumbers supported Revit elements sequentially in the order they are selected.

The workflow supports numeric and prefixed numbering sequences and automatically handles conflicts with values already in use.

------------------------------------------------------------------------

## Opening the Tool

On the **Flow** ribbon:

1.  Open **Annotation**.
2.  Choose **Renumber**.

The Annotation window hides while the Renumber workflow is active so the Revit canvas remains clear for model selection.

------------------------------------------------------------------------

## Supported Elements

The current native workflow supports:

  Target           Value changed
  ---------------- ---------------
  Rooms            Room Number
  Areas            Area Number
  MEP Spaces       Space Number
  Doors            Mark
  Walls            Mark
  Windows          Mark
  Parking Spaces   Mark
  Levels           Level Name
  Grids            Grid Name

------------------------------------------------------------------------

## Renumbering Elements

1.  Start **Renumber**.
2.  Choose the type of element to renumber.
3.  Enter the starting value.
4.  Select elements one by one in the required sequence.
5.  Press **Esc** when finished.
6.  Flow restores the Annotation window.

!!! tip "Selection order controls the sequence"

    Select elements in the exact order you want their new values assigned.

------------------------------------------------------------------------

## Starting Values

Renumber preserves prefixes and zero-padding.

Examples:

  Starting value   Sequence
  ---------------- ---------------------
  `1`              `1`, `2`, `3`
  `01`             `01`, `02`, `03`
  `D01`            `D01`, `D02`, `D03`
  `W10`            `W10`, `W11`, `W12`

This makes it suitable for common architectural mark and datum naming patterns.

------------------------------------------------------------------------

## Existing Value Conflicts

If a requested value is already used by another supported element, Flow handles the conflict through the shared numbering engine rather than requiring you to clear the existing values manually.

Review the resulting sequence after a large renumbering operation, particularly where the existing numbering is already dense.

------------------------------------------------------------------------

## Finishing with Escape

Press **Esc** when you have completed the selection sequence.

If elements have already been renumbered, those completed changes are retained.

If the workflow is cancelled before any changes are made, it leaves no Revit Undo item.

------------------------------------------------------------------------

## Undo

A completed Renumber session appears as a **single Revit Undo operation**.

This allows the complete interactive numbering session to be reversed in one step.

------------------------------------------------------------------------

## Current Scope

The current native sequential workflow does not include Viewport renumbering or Doors by Room.

These are not presented as available Renumber targets in this documentation.

------------------------------------------------------------------------

## Related Help

-   [Renumber Troubleshooting](troubleshooting.md)
-   [Grid Renumber](grid-renumber.md)
-   [Annotation](index.md)