# Pattern Manager Troubleshooting

Use these checks if a library or project pattern is missing, a definition cannot be saved, geometry generation fails or a filled-region operation cannot be completed.

---

## The Pattern Library Is Not Available

If Pattern Manager reports **Library not found**, **Library unavailable** or **Library error**:

1. Confirm that the configured hatch-pattern library location is accessible.
2. Confirm that the expected library folder has not been renamed or moved.
3. Check network or shared-storage access where applicable.
4. Click **Refresh**.

Pattern Manager scans all subfolders, so PAT files do not need to be stored directly in the library root.

---

## I Cannot Find a Library Pattern

1. Clear the library search.
2. Set the folder filter to **All Folders**.
3. Click **Refresh** if the PAT file was recently added or changed.
4. Review the library warning count and messages.
5. Confirm that the definition has a recognised target and at least one usable grid.

Search matches the pattern name and description, while the folder filter includes the selected folder and its descendants.

---

## A PAT File Produces Warnings

Review the reported filename, line number and pattern name where available.

Common causes include:

- invalid numeric grid data;
- missing or unsupported units;
- no model or drafting target declaration;
- a pattern header without a name; or
- no usable grids in the definition.

Correct the PAT file and click **Refresh**. Other valid patterns can remain available even when one file or definition produces warnings.

---

## A Library Pattern Does Not Create a New Project Pattern

Flow standardises the pattern name before loading it. If a pattern with the same standardised name and the same model or drafting target already exists, Flow returns that existing definition instead of creating a duplicate.

Check **Project Patterns** using the standardised `ADa_` name.

---

## A Project Pattern Is Missing

1. Clear the project search.
2. Set the type filter to **All Types**.
3. Confirm that the pattern is loaded in the active project.

Solid fill is intentionally excluded from Pattern Manager’s project-pattern list.

---

## A Pattern Cannot Be Saved

Read the validation message shown by Pattern Editor and check:

- the name is not empty or already used;
- the definition contains at least one grid;
- every grid has a valid, non-zero offset;
- dash and gap segments have non-zero lengths; and
- a segmented grid is not made only from gaps and dots.

Pattern Editor stays open after validation fails so the definition can be corrected.

---

## An Edited Project Pattern Cannot Be Updated

Flow must find the existing project pattern by its name and target before it can replace the definition.

The update can fail when:

- the original pattern no longer exists;
- its model or drafting target has changed unexpectedly;
- a temporary Flow update name already exists; or
- Revit rejects the resulting grid definition.

Review the message shown by Flow and check the current project-pattern list before retrying.

---

## Pattern Generation from Geometry Fails

Check the following:

1. Use a supported plan, section, detail, elevation or drafting view.
2. Select detail lines, model lines, supported curves or a filled region with a usable fill pattern.
3. Exclude unrelated or zero-length geometry.
4. Select one complete repeat of the intended pattern.
5. Pick two opposite tile corners with non-zero width and height.

If Flow reports that no grids could be generated, simplify the selection and confirm that it contains a repeatable family of lines.

Curves are converted to straight tessellated chords. Very complex curves can therefore create many grids and may need to be simplified first.

---

## The Generated Pattern Repeats Incorrectly

The most likely cause is the selected tile rather than the linework.

Try again and pick equivalent opposite corners of exactly one complete repeat. Avoid selecting a partial repeat or a rectangle covering several unequal repeats.

Also review the generated grid offsets, origins, shifts and segment sequences in Pattern Editor before saving.

---

## The Preview Looks Different from Revit

The Flow preview is intended for review and editing, but Revit remains the final reference for display.

Differences are most likely with:

- dense dot patterns;
- very short dash or gap segments;
- very large repeat spacing;
- complex tessellated curves; or
- model patterns viewed at a very different display scale.

Check the target and units, then load or save the pattern and review it in an appropriate Revit view.

---

## Merge or Cut Is Not Available

Open a supported graphical view. Merge and Cut are not available in unsupported view types such as schedules, sheets or non-graphical views.

Also confirm that an active Revit document is available.

---

## Merge Filled Regions Fails

Confirm that:

- at least two filled regions were selected for merging;
- a valid sample filled region was selected for the result type;
- the regions belong to the active view; and
- the combined boundaries can form a valid Revit filled region.

---

## Cut Filled Region Fails

Confirm that:

- one base filled region was selected;
- at least one cutter region was selected;
- the cutter geometry overlaps the intended base area; and
- the subtraction produces valid closed boundary loops.

---

## Create Filled Region Fails

Confirm that:

- the source project pattern is valid;
- the captured boundary consists of valid closed loops;
- existing linework is suitable for profile capture; and
- the active view supports filled regions.

If existing linework is unsuitable, retry using **Draw Boundary**.

---

## Reporting a Problem

If the problem continues, record:

- the Revit and Flow versions;
- the pattern name and whether it is a library or project pattern;
- the model or drafting target and units;
- the active Revit view type;
- the workflow being used;
- the exact message shown by Flow;
- the relevant PAT file where applicable; and
- screenshots of Pattern Manager and the affected Revit result.

---

## Related Help

- [Pattern Manager](index.md)
- [Browsing the Pattern Library](browsing-pattern-library.md)
- [Project Patterns](project-patterns.md)
- [Creating and Editing Patterns](creating-and-editing-patterns.md)
- [Generating Patterns from Geometry](generating-patterns-from-geometry.md)
- [Importing and Exporting Patterns](importing-and-exporting-patterns.md)
- [Filled Region Tools](filled-region-tools.md)