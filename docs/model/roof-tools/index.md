<a id="top"></a>

# Roof Tools

Roof Tools brings together specialised commands for roof modelling, documentation and detailing workflows in Revit.

The current toolset includes:

- **Roof Surface Zones** for creating ridge, hip and gable/verge flashing geometry;
- **Roof Outline** for generating a clean 2D exterior roof perimeter; and
- **Gutter Caps** for creating solid caps at the ends of Revit gutters.

---

## Open Roof Tools

Go to:

**Flow → Model → Roof**

The **Roof** window opens with the available roof tools.

<!-- SCREENSHOT: Roof window showing Roof Surface Zones, Roof Outline and Gutter Caps. -->

Select the required tool to begin.

Roof tools can also be launched directly from **Flow Hub** or the **Command Palette**.

---

## Roof Surface Zones

**Roof Surface Zones** creates modelled flashing zones along recognised roof ridges, hips and exposed gable or verge edges.

It can process one roof automatically or analyse several associated roof elements as one temporary assembly. The combined review workflow allows individual roof planes and edges to be corrected before the final DirectShape flashings are created.

[Learn how to use Roof Surface Zones](roof-surface-zones.md)

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

- [Roof Surface Zones](roof-surface-zones.md)
- [Roof Outline](roof-outline.md)
- [Gutter Caps](gutter-caps.md)
- [Roof Tools Troubleshooting](troubleshooting.md)

---

<div align="right">
  <a href="#top">🔝 Back to top</a>
</div>
