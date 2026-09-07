# Creating and Editing Patterns

Use **Pattern Editor** to build a new fill pattern or create a variation of an existing project pattern.

---

## Create a Blank Pattern

1. Open **ADAPT → Model → Patterns**.
2. Open the **Tools** tab.
3. Select **Blank Pattern**.

Pattern Editor opens with a new model pattern named **New Pattern**, using millimetres and one default grid.

---

## Pattern Properties

At the top of Pattern Editor:

- edit **Name** before Flow applies its standard project prefix; and
- review the read-only **Type** and **Units** values inherited from the source definition.

The current editor does not provide controls for changing Type, Units or Description.

### Model patterns

Model patterns represent real-world spacing and remain aligned to model geometry as the view scale changes.

### Drafting patterns

Drafting patterns represent printed graphics and scale with the view.

Revit stores model and drafting patterns separately and uses them for different purposes. Confirm the required type before opening the editor because it cannot currently be changed there.

---

## Work with Pattern Grids

A fill pattern contains one or more repeating grids. Each grid defines a family of parallel lines.

Use:

- **Add** to insert a new grid after the selected grid;
- **Duplicate** to copy the selected grid; and
- **Delete** to remove the selected grid.

At least one grid must remain.

For the selected grid, edit:

- **Angle** — line angle in degrees;
- **Offset** — perpendicular spacing between repeated lines;
- **Origin U** and **Origin V** — the grid origin;
- **Shift** — movement along the line direction between successive repeats; and
- the ordered **Dash**, **Gap** and **Dot** segment sequence.

Continuous lines do not require a dash sequence.

For segments, use **Add**, **Duplicate**, **Delete**, **Move Up** and **Move Down** to build the required order. A newly added segment is a 100 mm dash. Enter positive lengths for Dash and Gap; Flow writes Gap values as negative PAT segments. Dot segments always have a zero length.

---

## Scale or Rotate the Pattern

Use the pattern transformation controls to change the complete definition:

- enter a **Scale Factor** and click **Apply** to scale grid origins, offsets, shifts and dash or gap lengths; or
- enter a **Rotate (degrees)** value and click **Apply** to rotate grid origins about `0,0` and add the rotation to every grid angle.

These operations change the grid data itself. The values reset after a successful transformation so that another operation can be entered independently.

!!! tip "Duplicate before making a variation"

    If the source project pattern must remain unchanged, duplicate it first and apply scale or rotation to the copy.

---

## Use the Preview and Analysis

The preview updates from the current editor definition. Use it to check:

- overall direction and spacing;
- interaction between multiple grids;
- dash, gap and dot sequences; and
- the effect of scale or rotation.

Generated patterns may also show analysis information captured from the selected geometry.

The preview is indicative rather than a replacement for checking the final pattern in Revit, particularly for dense dots, very small segments or large repeat distances.

<!-- SCREENSHOT: Pattern Editor showing the definition fields, grid controls, segment editor and live preview. -->

---

## Duplicate a Project Pattern

1. Open **Project Patterns**.
2. Select or right-click the required pattern.
3. Choose **Duplicate**.

The copy opens in creation mode with ` - Copy` added to its name. Rename or edit it, then click **Save** to create a separate project pattern.

---

## Editing an Existing Project Pattern

1. Open **Project Patterns**.
2. Select the required pattern.
3. Click **Edit**.
4. Modify the definition.
5. Click **Save**.

!!! warning "Existing-pattern updates are not currently complete"

    The current update process creates a temporary replacement pattern but does not transfer project references back to it or remove the original definition. Do not rely on **Edit** for production changes yet. Use **Duplicate** to create a separate pattern, then deliberately reassign affected materials or filled-region types in Revit.

---

## Validation Before Saving

Pattern Editor prevents saving when:

- the name is empty, reserved as **Solid Fill**, or already used by another project pattern when creating or duplicating;
- no grids are present;
- a grid offset is invalid or zero;
- a dash or gap has a zero length; or
- a segmented grid contains only gaps and dots, with no drawable dash.

If validation fails, Pattern Editor remains open so the definition can be corrected.

If you close or cancel after making changes, Flow asks whether those unsaved changes should be discarded.

---

## Save the Pattern

Click **Save** after the definition passes validation.

- A new or duplicated pattern is added to the active Revit project.
- Existing-pattern editing is subject to the limitation described above.
- Saving in Pattern Editor does not write a PAT file. Use **Export** separately when a PAT file is required.

!!! note "Name-only edits"

    In the current editor, changing only the Name may not enable **Save** in Edit mode. Use **Conform Name** for ADa prefix corrections. For a genuinely new definition, use **Duplicate** instead.

---

## Related Help

- [Pattern Manager](index.md)
- [Project Patterns](project-patterns.md)
- [Generating Patterns from Geometry](generating-patterns-from-geometry.md)
- [Importing and Exporting Patterns](importing-and-exporting-patterns.md)
- [Troubleshooting](troubleshooting.md)