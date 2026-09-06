# Annotation Troubleshooting

Use this page when an **Annotation** tool does not produce the expected result.

Choose the relevant tool below, then work through the checks for the issue you are seeing.

------------------------------------------------------------------------

## Wall Dimensions

### The Tool Does Not Run

Check that a Revit project is open and that the active view is supported.

The source workflow accepts **Floor Plan** and **Reflected Ceiling Plan** views only. If you are in another view type, switch to a plan view and try again.

------------------------------------------------------------------------

### No Model Lines Were Accepted

Wall Dimensions relies on model lines to define the dimensioning path.

Check that:

1.  the selected elements are Revit **Model Lines**;
2.  the lines are visible in the active view;
3.  you completed the selection rather than cancelling it;
4.  the lines pass through or sufficiently close to the walls you want to dimension.

If no valid preselection exists, use the selection workflow offered by Flow.

------------------------------------------------------------------------

### No Dimensions Were Created

Flow needs at least two usable references to create a dimension.

Check whether:

-   the selected model line actually crosses the walls;
-   the walls belong to the active plan level;
-   the walls are parallel where a continuous string is expected;
-   the wall construction contains usable core information;
-   the wall geometry allows Revit to create stable dimension references.

Try a simpler line across two clearly parallel walls to isolate the problem.

------------------------------------------------------------------------

### Some Walls Were Skipped

Wall Dimensions groups compatible parallel walls. Walls that do not match the group direction or do not provide suitable references can be excluded.

If a wall is consistently missed, review its orientation, wall type and location relative to the model line.

------------------------------------------------------------------------

### A Model Line Disappeared

The source workflow deletes model lines after successful dimension creation.

If the current native tool retains this behaviour, this is expected. Use **Undo** if you need to restore the operation and review the setup.

------------------------------------------------------------------------

### The Result Is Not Where I Expected

The resulting dimension follows the selected model line. Check the position and direction of the model line before running the tool.

For more information, return to [Wall Dimensions](wall-dimensions.md).

------------------------------------------------------------------------

## Grid Dimensions

### The Tool Does Not Run

Check that:

-   a Revit project is open;
-   an active view is available;
-   the active view supports linear grid dimensions.

If the current view is unsupported, switch to a plan, section, elevation or detail view as appropriate.

------------------------------------------------------------------------

### No Dimension Types Are Available

Grid Dimensions requires at least one linear Revit Dimension Type.

Open the project dimension settings and confirm that a usable linear Dimension Type exists.

------------------------------------------------------------------------

### The Offset Was Rejected

Enter a positive numeric value in millimetres.

The source workflow uses **350 mm** when the entered value is invalid or non-positive.

------------------------------------------------------------------------

### No Usable Grids Were Found

Flow filters selected elements before dimensioning.

Check that:

1.  the elements are Revit grids;
2.  at least two grids match the selected orientation;
3.  the grids are parallel;
4.  they are not already dimensioned in the active view.

------------------------------------------------------------------------

### Only One Grid Was Accepted

A continuous grid dimension requires at least two usable grids.

Select another grid with the same orientation and try again.

------------------------------------------------------------------------

### Some Selected Grids Were Ignored

This normally means a grid:

-   did not match the selected orientation;
-   was already dimensioned in the active view;
-   could not be grouped with the other selected grids.

Run the tool again using a more consistent grid set.

------------------------------------------------------------------------

### The Dimension Is on the Wrong Side

Dimension placement is calculated from the selected grid orientation and the configured offset.

If the result is not useful for the drawing, review the grid orientation choice and offset, then rerun the workflow.

------------------------------------------------------------------------

## Join Dimensions

### The Selected Dimensions Were Not Joined

Join Dimensions requires at least two compatible dimensions.

Check that:

-   both elements are Revit dimensions;
-   they run in a compatible direction;
-   their references can form one valid continuous dimension;
-   the active view supports the selected dimensions.

Try joining a simple pair of aligned dimensions first.

------------------------------------------------------------------------

### A Dimension Has No Usable References

A replacement dimension can only be created where Revit exposes valid references from the source dimensions.

If Flow cannot collect at least two valid references after filtering, no replacement can be created.

------------------------------------------------------------------------

### The Dimensions Run in Different Directions

Perpendicular or otherwise incompatible dimension strings cannot be combined into one linear dimension.

Select only dimensions describing the same dimension direction.

------------------------------------------------------------------------

### A Zero-Length Segment Prevented the Join

Duplicate or near-identical references can create a zero-length dimension segment.

Flow attempts to remove references that would create invalid zero-length segments. If a valid string still cannot be produced, the join is not completed.

Review the original dimension references and remove redundant source dimensions or references before trying again.

------------------------------------------------------------------------

### A Segment Label Was Not Preserved

Join Dimensions preserves supported **Below** labels by matching their positions to the recreated dimension segments.

A label may not be restored where:

-   the corresponding segment no longer exists;
-   references were removed to prevent an invalid segment;
-   the replacement geometry changes the segment position too much.

Check the recreated dimension and reapply the label with **Dimension Labels** if required.

------------------------------------------------------------------------

### The Original Dimensions Are Still Present

This usually means the replacement dimension could not be created successfully.

The intended workflow keeps source dimensions until successful replacement is confirmed.

------------------------------------------------------------------------

### Escape Ended the Tool

This is normal. **Esc** finishes the repeated selection workflow.

Any completed joins should remain in the model.

------------------------------------------------------------------------

## Dimension Labels

### The Tool Does Not Run

The verified source workflow is limited to **Floor Plan** and **Reflected Ceiling Plan** views.

Switch to a supported plan view and try again.

------------------------------------------------------------------------

### The Selected Dimension Has No Segments

Dimension Labels requires a continuous dimension chain containing individual segments.

If the selected dimension is a single unsegmented dimension, choose a different dimension chain.

------------------------------------------------------------------------

### The Wrong Segment Was Labelled

Flow identifies the segment whose origin is closest to the point you click.

Undo the change if required, run the tool again and click closer to the intended dimension segment.

------------------------------------------------------------------------

### The Room Tag Was Not Accepted

Select a Revit **Room Tag**.

Other annotation tags are not valid for the verified room-label workflow.

------------------------------------------------------------------------

### Flow Could Not Find the Room

The selected Room Tag must resolve to a valid Revit Room.

Check that:

-   the tag is associated with a room;
-   the room still exists;
-   the tag is not orphaned;
-   the room has a usable **Name** value.

------------------------------------------------------------------------

### The Label Is Blank

The workflow writes the Room **Name** to the dimension segment.

If the Room Name is blank, the resulting segment label will also be blank.

------------------------------------------------------------------------

### A Label Changed After Joining Dimensions

Join Dimensions attempts to preserve supported segment labels, but a label may not be matched if the recreated dimension has materially different segments.

Reapply the label with **Dimension Labels** if necessary.

------------------------------------------------------------------------

## Auto Tag

### No Tag Types Are Available

Auto Tag requires a compatible tag family/type to be loaded in the project.

For the verified downpipe workflow, the source implementation looks for the configured downpipe tag-family naming convention.

Load the required tag family and try again.

------------------------------------------------------------------------

### No Supported Elements Were Found

Auto Tag searches the active view for supported elements.

For the verified downpipe workflow, the source implementation looks for downpipe family instances in the **Plumbing Fixtures** category using the configured downpipe family naming convention.

Check that:

-   the required elements exist in the active view;
-   the correct families are being used;
-   the elements are visible to the view.

------------------------------------------------------------------------

### Some Elements Were Not Tagged

Auto Tag deliberately skips elements that are already tagged in the active view.

If an element appears untagged, check for an existing tag that references it but has been moved away from the element.

------------------------------------------------------------------------

### A Tag Was Placed in an Unexpected Position

The source workflow places the tag at the element location point where available, otherwise at the centre of the element bounding box.

Move individual tags manually after creation where drawing composition requires adjustment.

------------------------------------------------------------------------

### The View Template Changed

The source workflow temporarily detaches the active view template during tag creation and restores it afterwards.

If the view does not appear as expected after the operation, check the active view template and category visibility settings.

------------------------------------------------------------------------

### No Tags Were Created

Check both sides of the workflow:

1.  a compatible tag type must be available;
2.  at least one supported untagged element must exist in the active view.

Return to [Auto Tag](auto-tag.md) and run the workflow again.

------------------------------------------------------------------------

## Text Tools

### No Text Was Changed

Check that the selected elements are Revit **Text Notes**.

Text in tags, dimensions, schedules, family labels or other annotation types is not part of the verified Text Note workflow.

------------------------------------------------------------------------

### Nothing Was Selected

If no valid Text Notes are preselected, select Text Notes when prompted.

Press **Esc** only after you have picked all required notes.

------------------------------------------------------------------------

### The Text Already Matches the Selected Case

Flow does not rewrite a Text Note when the transformed text would be identical to the current text.

This means the reported changed count can be lower than the number of selected notes.

------------------------------------------------------------------------

### Technical Abbreviations Did Not Change

Sentence Case and Title Case intentionally preserve recognised technical terms, all-capital tokens and tokens containing numbers.

This prevents terms such as **NZBC**, **FFL**, **BIM** and similar documentation abbreviations from being changed incorrectly.

------------------------------------------------------------------------

### Bold, Italic or Underline Formatting Disappeared

The verified source workflow resets changed Text Notes to plain text.

Use **Undo** if the formatting needs to be retained.

------------------------------------------------------------------------

### Some Notes Failed

A Text Note can fail if Revit does not allow its text to be rewritten.

Try the affected note individually. If it still fails, check whether the note or its parameter is read-only or otherwise controlled.

------------------------------------------------------------------------

## Grid Renumber

### The Starting Value Was Rejected

The verified Grid Renumber source workflow accepts a numeric starting value.

Enter a valid number and try again.

------------------------------------------------------------------------

### A Selected Element Was Not Renumbered

Grid Renumber accepts Revit grids only.

If another element was picked, select the required grid and continue.

------------------------------------------------------------------------

### The Numbers Are in the Wrong Order

Grid numbers are assigned in selection order.

Use **Undo** and rerun the workflow, selecting the grids in the required order.

------------------------------------------------------------------------

### An Existing Grid Number Changed Unexpectedly

When a requested number is already in use, the verified source workflow moves the conflicting grid to the next available number.

Review the overall grid sequence after a substantial renumbering operation.

------------------------------------------------------------------------

### Temporary Graphics Remained in the View

The source workflow removes its temporary visual marking when the session finishes.

If temporary overrides remain, complete or cancel the workflow and refresh the view. If the issue persists, use **Undo** and report the problem.

------------------------------------------------------------------------

### Escape Ended the Selection

This is expected. **Esc** finishes the interactive grid selection sequence.

------------------------------------------------------------------------

## Renumber

### The Target Type Is Not Available

The current native Renumber workflow supports:

-   Rooms
-   Areas
-   MEP Spaces
-   Doors
-   Walls
-   Windows
-   Parking Spaces
-   Levels
-   Grids

Viewport renumbering and Doors by Room are not part of the current connected workflow.

------------------------------------------------------------------------

### The Starting Value Was Not Accepted

Enter a valid starting sequence.

Renumber supports values such as:

-   `1`
-   `01`
-   `D01`
-   `W10`

Prefixes and zero-padding are preserved as the sequence increments.

------------------------------------------------------------------------

### An Element Cannot Be Selected

Renumber filters model selection to the target type chosen at the start of the workflow.

For example, if **Doors** is selected as the target, picking a wall does not renumber it.

Choose the correct target type and select the required elements again.

------------------------------------------------------------------------

### An Existing Value Changed

When the requested value is already in use, Flow resolves the conflict through the shared numbering engine.

This may cause another element's existing value to move so the requested sequence can be applied.

Review the affected numbering after the operation.

------------------------------------------------------------------------

### The Annotation Window Disappeared

This is expected.

Flow hides the Annotation and Renumber choice windows before Revit model picking begins so they do not obstruct the Revit canvas.

The Annotation window is restored when the Renumber workflow finishes.

------------------------------------------------------------------------

### Escape Finished the Tool

This is normal.

**Esc** ends the interactive selection sequence. Any completed numbering changes remain.

If no elements were changed before cancellation, no Revit Undo item is created.

------------------------------------------------------------------------

### Undo Reverts the Whole Session

A completed Renumber session is grouped into a single Revit Undo operation.

Use **Undo** once to reverse the complete session.

------------------------------------------------------------------------

## Related Help

-   [Annotation](index.md)
-   [Wall Dimensions](wall-dimensions.md)
-   [Grid Dimensions](grid-dimensions.md)
-   [Join Dimensions](join-dimensions.md)
-   [Dimension Labels](dimension-labels.md)
-   [Auto Tag](auto-tag.md)
-   [Text Tools](text-tools.md)
-   [Grid Renumber](grid-renumber.md)
-   [Renumber](renumber.md)