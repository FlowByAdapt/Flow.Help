# Roof Tools

Roof Tools brings together specialised commands for roof documentation and detailing workflows in Revit.

The current toolset includes **Roof Outline** for generating a clean 2D exterior roof perimeter and **Gutter Caps** for creating solid caps at the ends of Revit gutters.

---

## Open Roof Tools

Go to:

**Flow → Model → Roof**

The **Roof** window opens with the available roof tools.

<!-- SCREENSHOT: Roof window showing the Roof Outline and Gutter Caps cards. -->

Select the required tool to begin.

Both **Roof Outline** and **Gutter Caps** can also be launched directly from **Flow Hub**.

---

## Roof Outline

**Roof Outline** creates a clean 2D outline around the exterior perimeter of one or more adjoining Revit Roof by Footprint elements.

Flow reads the selected roof footprints, removes shared edges and determines the exterior boundary of the combined roof shape.

The resulting outline is created as Detail Lines in the active plan view using the `Roof_Outline` line style.

[Learn how to use Roof Outline](roof-outline.md)

---

## Gutter Caps

**Gutter Caps** creates a small solid cap at a selected end of a Revit gutter without requiring a separate cap family.

Flow derives the cap from the actual gutter-end geometry. A single gutter can be processed at both ends in one run, and Flow checks for an existing generated cap before creating another.

Gutter Caps also finds and activates a suitable **Roof Plan** automatically where required.

[Learn how to use Gutter Caps](gutter-caps.md)

---

## Related Help

- [Roof Outline](roof-outline.md)
- [Gutter Caps](gutter-caps.md)
- [Roof Tools Troubleshooting](troubleshooting.md)