# Creating and Editing Patterns

Use **Pattern Editor** to build a new fill pattern, create a variation of an existing project pattern, or update an existing definition.

---

## Create a Blank Pattern

1. Open **Flow → Model → Patterns**.
2. Open the **Tools** tab.
3. Select **Blank Pattern**.

Pattern Editor opens with a new model pattern named **New Pattern**, using millimetres and one default grid.

---

## Pattern Properties

At the top of Pattern Editor, set:

- **Name** — the project pattern name before Flow applies its standard project prefix;
- **Target** — **Model** or **Drafting**;
- **Units** — **Millimetres** or **Inches**; and
- **Description** — explanatory text retained in the pattern definition and PAT export.

### Model patterns

Model patterns represent real-world spacing and remain aligned to model geometry as the view scale changes.

### Drafting patterns

Drafting patterns represent printed graphics and scale with the view.

Choose the target deliberately. Revit stores model and drafting patterns separately and uses them for different purposes.

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

---

## Scale or Rotate the Pattern

Use the pattern transformation controls to change the complete definition:

- enter a **Scale Factor** and click **Apply** to scale all pattern dimensions; or
- enter a **Rotation** angle and click **Apply** to rotate every grid.

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

---

## Duplicate a Project Pattern

1. Open **Project Patterns**.
2. Select or right-click the required pattern.
3. Choose **Duplicate**.

The copy opens in creation mode with ` - Copy` added to its name. Rename or edit it, then click **Save** to create a separate project pattern.

---

## Edit a Project Pattern

1. Open **Project Patterns**.
2. Select the required pattern.
3. Click **Edit**.
4. Modify the definition.
5. Click **Save**.

Flow updates the existing project pattern rather than creating a separate definition.

---

## Validation Before Saving

Pattern Editor prevents saving when:

- the name is empty or already used by another project pattern;
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
- An edited project pattern updates the existing Revit definition.
- Saving in Pattern Editor does not write a PAT file. Use **Export** separately when a PAT file is required.

---

## Related Help

- [Pattern Manager](index.md)
- [Project Patterns](project-patterns.md)
- [Generating Patterns from Geometry](generating-patterns-from-geometry.md)
- [Importing and Exporting Patterns](importing-and-exporting-patterns.md)
- [Troubleshooting](troubleshooting.md)