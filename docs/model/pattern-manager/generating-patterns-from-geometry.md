# Generating Patterns from Geometry

Use **From Geometry** to convert existing Revit linework or a filled-region pattern into an editable fill-pattern definition.

---

## Before You Start

Open a supported graphical view containing the source geometry.

Supported views include:

- floor and ceiling plans;
- engineering and area plans;
- sections and details;
- elevations; and
- drafting views.

The source can include:

- detail lines;
- model lines;
- line-based curves that Revit can tessellate, including arcs, ellipses and splines; and
- filled regions with a usable foreground or background fill pattern.

For linework, draw or identify one complete rectangular repeat of the pattern. The two tile corners selected later define the repeat width and height.

!!! tip "Use clean, repeatable geometry"

    Results are most predictable when the selected linework represents one complete repeat and unnecessary construction geometry is excluded.

---

## Start From Geometry

1. Open **Flow → Model → Patterns**.
2. Open the **Tools** tab.
3. Select **From Geometry**.

Pattern Manager temporarily hides while Revit handles the selection.

---

## Select the Source Geometry

1. Select the detail linework, model linework or filled region that defines the pattern.
2. Click **Finish** on Revit’s selection controls.

Flow projects the selected geometry onto the active view plane.

Straight linework is analysed into families of repeated parallel lines. Curved elements are tessellated into straight chords, with each usable chord compiled as a finite repeating pattern grid.

If a filled region is selected, Flow reads its usable fill grids directly. The filled-region boundary is not used as hatch geometry.

---

## Define the Repeating Tile

After selecting the source geometry:

1. Pick the first corner of the repeating pattern tile.
2. Pick the opposite corner.

The two points must create a tile with non-zero width and height.

The tile establishes the repeat dimensions used when Flow compiles the selected line families into Revit pattern grids.

!!! note "The tile controls repetition"

    Pick equivalent opposite corners of one complete repeat. An incorrect tile can produce unexpected spacing, shifting or discontinuities even when the selected linework itself looks correct.

---

## Review the Generated Definition

If usable grids are generated, Pattern Editor opens with:

- the name **New Geometry Pattern**;
- the description **Generated from Revit linework**;
- **Model** as the initial target;
- **Millimetres** as the initial units; and
- the compiled grid and segment definitions.

These are starting values. Rename the pattern and change its target, units or grid properties where required.

Review the preview and any available analysis information. For detailed control, edit individual grid angles, offsets, origins, shifts and segment sequences before saving.

---

## Create the Project Pattern

1. Enter a unique pattern name.
2. Confirm **Model** or **Drafting**.
3. Review the units and generated grids.
4. Click **Save**.

Flow validates the definition and loads it into the active Revit project.

---

## If Geometry Is Rejected

Flow reports a message when:

- no active graphical view is available;
- the active view type is unsupported;
- no geometry is selected;
- selected elements contain no usable linework or fill grids;
- the chosen tile has zero width or height; or
- no supported pattern grids can be compiled.

Canceling either the geometry selection or a tile-corner pick cancels the workflow without creating a pattern.

---

## Acknowledgement

This workflow is Flow’s native implementation of pattern-generation ideas demonstrated by the pyRevit pattern-making tools. Flow extends the workflow through its Pattern Editor, project-pattern management and filled-region integration.

---

## Related Help

- [Pattern Manager](index.md)
- [Creating and Editing Patterns](creating-and-editing-patterns.md)
- [Filled Region Tools](filled-region-tools.md)
- [Troubleshooting](troubleshooting.md)