# Annotation Troubleshooting

Use this page when an **Annotation** tool does not produce the expected result.

Choose the relevant tool below, then work through the checks for the issue you are seeing.

---

## Wall Dimensions

### The Tool Does Not Run

Check that a Revit project is open and that the active view is supported.

**Wall Dimensions** can be used in:

* **Floor Plans**
* **Reflected Ceiling Plans**

If you are in another view type, switch to a supported plan view and try again.

### No Dimension Was Created

Flow needs at least two usable wall-core references to create a dimension.

Check whether:

* the dimension path crosses or passes sufficiently close to the required walls;
* the walls are straight;
* the walls are perpendicular to the dimension path;
* the walls belong to the active plan level;
* the wall construction contains usable core information.

Try drawing a simple path across two straight, parallel walls to isolate the problem.

### Some Walls Were Skipped

Flow filters the walls discovered along the dimension path before creating the dimension.

A wall may be excluded if:

* it is curved;
* it is not perpendicular to the dimension path;
* it is hosted on a different level;
* its core locations cannot be resolved;
* suitable supporting references cannot be created.

For predictable results, draw the path across the walls rather than along them.

### The Dimension Path Does Not Follow the Expected Direction

Flow normally assists with constraining the dimension path based on walls in the active plan.

If you need a simple horizontal or vertical path, hold **Ctrl** while positioning the path.

### The Dimension Is Not Where I Expected

The dimension path determines which walls Flow investigates.

After accepting the path, Flow separately prompts:

> Pick the dimension line location.

This second point controls where the resulting dimension string is placed.

If the dimension is on the wrong side of the walls or too close to the model, use **Undo** and repeat the workflow, choosing a different dimension line location.

### Flow Supporting References

Wall Dimensions creates supporting references at resolved wall-core positions so Revit can maintain the resulting dimension.

Flow manages these references automatically.

When Wall Dimensions starts, it checks for orphaned Flow wall-dimension references and incomplete dimension sets in the active view and removes them where appropriate.

You should not need to create, edit or maintain these references manually.

For more information, return to [Wall Dimensions](wall-dimensions.md).

---

## Grid Dimensions

### The Tool Does Not Run

Check that:

* a Revit project is open;
* an active view is available;
* the active view supports Grid Dimensions.

Supported views include:

* Floor Plans
* Reflected Ceiling Plans
* Engineering Plans
* Area Plans
* Sections
* Elevations
* Detail Views

### No Dimension Types Are Available

Grid Dimensions uses linear Dimension Types whose names begin with **ADa**.

If no suitable types are available, check that the project contains an appropriate linear Dimension Type using the required naming convention.

Where **ADa_Blue** is available, Flow prioritises it as the initial type.

### No Usable Grids Were Found

A grid dimension requires at least two usable grids.

Check that:

* the selected elements are Revit Grids;
* at least two suitable grids remain after filtering;
* the grids are straight;
* the grids are not already dimensioned in the active view.

If too few usable grids remain, Flow prompts you to make another selection.

### Some Selected Grids Were Ignored

Flow automatically filters and groups the selected grids.

A grid may be excluded because:

* it is already dimensioned in the active view;
* it is curved;
* it cannot provide a usable linear grid reference.

Flow may report grids that were excluded because they are already dimensioned.

### Grids Were Split into Separate Dimensions

This is expected when the selection contains grids running in different directions.

Flow automatically groups compatible parallel grids and creates a separate dimension for each usable group.

You do not need to separate horizontal, vertical or angled grid sets before selecting them.

### The Dimension Is Not Where I Expected

Grid Dimensions does not use a predefined offset.

Flow asks you to pick the dimension location for each grid group.

Use **Undo** and repeat the workflow if you need to reposition the resulting dimension.

### Escape Ended the Workflow

This is normal.

Pressing **Esc** during grid selection or placement finishes the interactive workflow.

Any dimensions already completed remain in the model.

For more information, return to [Grid Dimensions](grid-dimensions.md).

---

## Join Dimensions

### The Selected Dimensions Were Not Joined

Join Dimensions requires at least two compatible dimensions.

Check that:

* the selected elements are linear Revit dimensions;
* the dimensions belong to the active view;
* they run in compatible parallel directions;
* their references can form a valid continuous dimension.

Try joining a simple pair of aligned dimensions first.

### A Dimension Has No Usable References

A replacement dimension can only be created where Revit exposes valid references from the source dimensions.

If Flow cannot collect at least two usable references after filtering, a replacement dimension cannot be created.

### The Dimensions Run in Different Directions

Perpendicular or otherwise incompatible dimension strings cannot be combined into one linear dimension.

The first dimension you select establishes the primary dimension direction and baseline.

Select additional dimensions that run parallel to it.

### A Zero-Length Segment Prevented the Join

Duplicate or redundant references can produce a zero-length dimension segment.

Flow attempts to remove the reference responsible for the zero-length segment and retries dimension creation.

This continues until a valid replacement can be created or there are not enough usable references remaining.

### A Below Label Was Not Preserved

Join Dimensions preserves supported **Below** labels by matching their positions to the recreated dimension segments.

A label may not be restored where:

* the corresponding segment no longer exists;
* a reference was removed to prevent an invalid segment;
* the recreated geometry changes the segment position too much.

Reapply the label with **Dimension Labels** if required.

### The Original Dimensions Are Still Present

This normally means a valid replacement dimension was not created.

Flow does not delete the source dimensions until the replacement dimension has been successfully created and supported Below labels have been reapplied.

### Escape Ended the Tool

This is normal.

**Esc** finishes the repeated dimension-selection workflow. Any completed joins remain in the model.

For more information, return to [Join Dimensions](join-dimensions.md).

---

## Dimension Labels

### The Tool Does Not Run

Dimension Labels can be used in:

* **Floor Plans**
* **Reflected Ceiling Plans**

Switch to a supported plan view and try again.

### The Selected Dimension Has No Segments

Dimension Labels applies a Room Name to an individual segment of a continuous dimension.

If the selected dimension is a single unsegmented dimension, choose a continuous dimension chain instead.

### The Wrong Segment Was Labelled

Flow identifies the dimension segment whose origin is closest to the point you click.

Use **Undo** if required, then repeat the workflow and click closer to the intended segment.

### The Room Tag Was Not Accepted

Select a Revit **Room Tag**.

Other annotation tags are not valid for the Room Name workflow.

### Flow Could Not Find the Room

The selected Room Tag must resolve to a valid Revit Room.

Check that:

* the tag is associated with a Room;
* the Room still exists;
* the tag is not orphaned;
* the Room has a usable **Name**.

### The Label Is Blank

Dimension Labels writes the Room **Name** to the dimension segment's **Below** label.

Check that the selected Room has a suitable Name value.

### An Existing Below Label Was Replaced

This is expected.

Dimension Labels writes the selected Room Name to the segment's **Below** label. Any existing Below text on that segment is replaced.

### A Label Changed After Joining Dimensions

Join Dimensions attempts to preserve supported Below labels, but a label may not be matched if the recreated dimension has materially different segments.

Reapply the label with **Dimension Labels** if necessary.

For more information, return to [Dimension Labels](dimension-labels.md).

---

## Auto Tag

### The Required Tag Family Is Missing

The current **Auto Tag → Downpipes** workflow uses configured tag families according to the downpipe category.

Flow requires:

* **Plumbing Fixtures:** `ADa_TAG_plum : Tag_plum`
* **Generic Models:** `ADa_TAG_Multi-Cat-Mark`

If the required tag is not available, load the appropriate Flow tag family into the project and try again.

### No Downpipes Were Found

Auto Tag searches the active view for supported downpipe family instances.

The current workflow recognises downpipes in:

* **Plumbing Fixtures**
* **Generic Models**

Check that the required downpipes exist and are available in the active view.

### Some Downpipes Were Not Tagged

Flow deliberately skips a downpipe if it already has an Independent Tag in the active view.

The existing tag does not need to have been created by Flow.

If a downpipe appears untagged, check whether an existing tag references it but has been moved elsewhere in the view.

A downpipe can also be skipped if Flow cannot determine a usable tag location.

### A Tag Was Placed in an Unexpected Position

Flow places each new tag at the element Location Point where available.

If that is unavailable, it attempts to use the centre of the element's bounding box.

Move individual tags manually after creation where drawing composition requires adjustment.

### No Tags Were Created

Check that:

1. supported downpipes exist in the active view;
2. the appropriate configured tag family is loaded;
3. the downpipes do not already have tags in the active view.

If all supported downpipes are already tagged, Flow reports that no untagged downpipes were found.

For more information, return to [Auto Tag](auto-tag.md).

---

## Text Tools

### No Text Was Changed

Check that the selected elements are Revit **Text Notes**.

Text contained in tags, dimensions, schedules, family labels or other annotation types is not part of the Text Tools case workflow.

### Nothing Was Selected

If valid Text Notes are preselected when Text Tools starts, Flow uses those notes.

If there are no valid preselected Text Notes, select the required notes when prompted and press **Esc** when the selection is complete.

If the current selection contains Text Notes and other element types, Flow uses the valid Text Notes and ignores the other elements.

### The Text Already Matches the Selected Case

Flow does not rewrite a Text Note when the transformed text would be identical to its current text.

A selected note may therefore remain unchanged even though the operation completed successfully.

### Technical Terms Did Not Change

Text Tools deliberately preserves recognised technical terminology where appropriate.

Examples include:

* **NZBC**
* **FFL**
* **BIM**
* **Revit**
* **pyRevit**
* **ADa**
* **GIB**
* **DWG**
* **IFC**

Sentence Case and Title Case also preserve applicable tokens containing numbers.

This behaviour prevents common technical terms from being changed into inappropriate case formats.

!!! note "Not every uppercase word is protected"

	Text Tools does not treat every arbitrary all-capital word as a protected technical term.

	Preservation depends on the selected case operation and the terminology recognised by Flow.

### Text Formatting Was Not Preserved

Flow attempts to preserve supported character formatting when changing text case, including:

* Bold
* Italic
* Underline
* Superscript
* Subscript
* All Caps

Where the text can be safely rewritten using Revit's formatted-text system, Flow records and reapplies this formatting.

If formatted-text editing fails, Flow may fall back to plain-text assignment. Character formatting may be lost in that situation.

Use **Undo** if the resulting formatting is not acceptable.

### Some Notes Failed

A Text Note may fail if Revit does not allow its text to be rewritten.

When failures occur, Flow reports the number of notes changed and the number that failed.

Try an affected note individually if you need to isolate the problem.

For more information, return to [Text Tools](text-tools.md).

---

## Grid Renumber

### The Starting Value Was Rejected

Grid Renumber supports several sequence formats, including:

* numeric — `1`, `2`, `3`
* zero-padded numeric — `01`, `02`, `03`
* alphabetic — `A`, `B`, `C`
* lowercase alphabetic — `a`, `b`, `c`
* prefixed numeric — `G01`, `G02`, `G03`

Enter a valid starting sequence and try again.

### A Selected Element Was Not Renumbered

Grid Renumber accepts Revit Grids only.

If another element is picked, select the required Grid and continue.

The same Grid cannot be processed twice during one renumbering session.

### The Numbers Are in the Wrong Order

Grid numbers are assigned in the order you select the Grids.

Use **Undo** and rerun the workflow, selecting them in the required sequence.

### An Existing Grid Number Changed Unexpectedly

When the requested Grid number is already in use, Flow resolves the conflict so the requested sequence can continue.

This can cause the Grid currently using that value to be moved to another available value.

Review the overall Grid sequence after a substantial renumbering operation.

### Temporary Graphics Remained in the View

Grid Renumber uses temporary view overrides to provide visual feedback while you work.

These overrides are restored when the session finishes.

If an override appears to remain, finish or cancel the workflow and refresh the view.

### Escape Ended the Selection

This is expected.

**Esc** finishes the interactive Grid selection sequence.

Changes already applied during the session remain and are grouped into the completed Revit operation.

For more information, return to [Grid Renumber](grid-renumber.md).

---

## Renumber

### The Target Type Is Not Available

Renumber only displays target types that are available for the current Revit context.

Supported targets include:

* Rooms
* Areas
* Doors
* Walls
* Windows
* Levels
* Grids
* Viewports

Not every target is available in every view.

If the required type is missing, open a view appropriate to that element type and start **Renumber** again.

### The Starting Value Was Not Accepted

Renumber supports numeric, alphabetic and combined sequences.

Examples include:

* `1`
* `01`
* `A`
* `a`
* `D01`
* `W10`

Prefixes and zero-padding are preserved as the sequence increments.

Enter a valid starting value and try again.

### An Element Cannot Be Selected

Renumber filters Revit selection to the target type chosen at the start of the workflow.

For example, if **Walls** is selected, a Door cannot be processed during that session.

Choose the correct target type and try again.

### An Existing Value Changed

When a requested value is already in use, Flow resolves the conflict through the shared numbering system.

This may cause another element's existing value to move so the requested sequence can be applied.

Review the affected numbering after a substantial renumbering operation.

### Doors by Room Is Not Available

The **By Room** option is available when **Doors** is selected as the Renumber target.

Doors by Room requires a plan view.

If the option cannot be used, switch to an appropriate plan view and start Renumber again.

### A Door Could Not Be Numbered by Room

Doors by Room uses the Room associated with the Door in the active phase.

Check that:

* the Door has **New** phase status in the active phase;
* the Door is associated with the required Room;
* the Room has a usable **Number**;
* the active view has a valid phase.

If Flow can identify exactly one associated Room, it uses that Room automatically.

If the Door could relate to more than one Room, Flow asks you to select the required Room.

### The Annotation Window Disappeared

This is expected.

Flow hides choice windows while Revit model interaction is required so they do not obstruct the canvas.

The workflow manages the window state as you move between Flow controls and Revit selection.

### Escape Finished the Tool

This is normal.

**Esc** ends the interactive selection sequence.

Any completed numbering changes remain. If nothing was changed during the session, the operation is rolled back rather than creating an unnecessary Revit Undo item.

### Undo Reverts the Whole Session

A completed interactive Renumber session is grouped into a single Revit operation.

Use **Undo** once to reverse the completed session.

For more information, return to [Renumber](renumber.md).

---

## Related Help

* [Annotation](index.md)
* [Wall Dimensions](wall-dimensions.md)
* [Grid Dimensions](grid-dimensions.md)
* [Join Dimensions](join-dimensions.md)
* [Dimension Labels](dimension-labels.md)
* [Auto Tag](auto-tag.md)
* [Text Tools](text-tools.md)
* [Grid Renumber](grid-renumber.md)
* [Renumber](renumber.md)