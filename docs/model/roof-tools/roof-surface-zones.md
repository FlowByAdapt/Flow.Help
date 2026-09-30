<a id="top"></a>

# Roof Surface Zones

**Roof Surface Zones** creates modelled flashing zones along recognised roof ridges, hips and exposed gable or verge edges.

The tool can process a single Revit roof automatically or analyse several associated roof elements as one temporary assembly. A review workflow is available for correcting the combined result before the final flashings are created.

**Ribbon:** Flow → Model → Roof → Roof Surface Zones

---

## When to Use Roof Surface Zones

Use Roof Surface Zones when you need to:

- create consistent ridge, hip and gable/verge flashing geometry;
- apply user-defined flashing widths across sloping roof faces;
- extend flashing beyond visible fascia edges;
- close exposed gable ends with a vertical downstand;
- analyse a roof constructed from several associated Revit roof elements; or
- preview and correct flashing edges on a complex combined roof.

The generated flashings are separate **Generic Model DirectShape** elements. The selected Revit roofs are not modified.

---

## Opening Roof Surface Zones

You can open the tool in either of two ways.

### From the Flow ribbon

Go to:

**Flow → Model → Roof**

Select **Roof Surface Zones** from the Roof window.

### From Flow Hub or Command Palette

Search for and run:

**Roof Surface Zones**

<!-- SCREENSHOT: Roof Surface Zones settings window showing production labels and default values. -->

---

## Before You Start

Check that:

- the required roofs are visible and selectable;
- the roof surfaces are planar;
- the roof boundaries use straight edges where flashings are required; and
- the material entered in the tool exists in the current Revit project.

The default material is:

`*ROF.SHEET_Flashing`

Roof Surface Zones analyses upper planar roof faces. Curved, non-planar, shape-edited or unusually constructed roof geometry may not produce a complete result.

---

## Flashing Settings

### Ridge flashing

Creates flashing along recognised horizontal ridge junctions.

The default width is **200 mm**.

### Hip flashing

Creates flashing along recognised external sloping hip junctions.

The default width is **200 mm**.

### Gable / verge flashing

Creates flashing along recognised exposed sloping roof edges.

The default width is **200 mm**.

### Fascia overhang

Controls how far applicable flashing extends beyond a visible fascia edge.

The default overhang is **25 mm**.

### Gable downstand

Controls the depth of the vertical return used to close an exposed gable end.

The default downstand is **75 mm**.

### Material name

Specifies the Revit material applied to the generated flashing faces.

The material must already exist in the project.

### Manually added flashing width

Controls the width used when **Add Flashing Edge** is used during combined-roof review.

The default manual width is **200 mm**.

All widths are entered in millimetres and are measured across the sloping roof face.

---

## Create Flashings on One Roof

Use the single-roof automatic workflow for a roof created as one Revit roof element.

1. Open **Roof Surface Zones**.
2. Select the required ridge, hip and gable/verge flashing types.
3. Enter the required widths, fascia overhang and gable downstand.
4. Confirm the material name.
5. Leave **Analyse associated roof parts together** cleared.
6. Select **Create Zones**.
7. Select the Revit roof when prompted.
8. If existing Flow flashings are detected, choose how they should be handled.
9. Review the completed result.

Flow analyses all supported upper faces of the selected roof and creates the qualifying flashing zones automatically.

<!-- SCREENSHOT: Before and after view of a simple roof showing ridge, hip and gable/verge flashings. -->

---

## Analyse Associated Roof Parts Together

Use combined analysis when several Revit roof elements form one physical roof.

1. Open **Roof Surface Zones**.
2. Configure the flashing settings.
3. Select **Analyse associated roof parts together**.
4. Select **Create Zones**.
5. Select all associated roof elements.
6. Click **Finish** in Revit to complete the selection.
7. If existing Flow flashings are detected, choose how they should be handled.
8. Review the completed result.

Flow analyses the selected roof elements as one temporary assembly. Matching coincident edges between separate roof elements are treated as shared junctions rather than exposed roof edges.

!!! tip

    Select every roof element that contributes to the physical roof assembly. Leaving out a connected roof part can cause the shared junction to be treated as an exposed edge.

---

## Review and Correct a Combined Result

Enable **Review and correct combined result** when the automatic combined result needs to be checked or adjusted before final creation.

### 1. Select the associated roofs

Select all roof elements that form the required assembly, then click **Finish** in Revit.

### 2. Review the complete preview

Flow displays the automatic flashing preview for the full combined roof.

At this stage you can:

- select **Finish** to accept the complete preview; or
- select **Select Roof Plane** to correct an individual plane.

<!-- SCREENSHOT: Complete combined-roof preview with the Roof Plane Flashing Editor at the top-left of the Revit canvas. -->

### 3. Select a roof plane

Select the physical sloping roof plane that requires correction.

The complete combined preview remains visible for context.

### 4. Correct the selected plane

Use the available editor actions as required.

#### Add Flashing Edge

Adds selected roof-profile edges using the **Manually added flashing width** and the standard fascia-overhang behaviour.

Use this for a general flashing edge that the automatic analysis omitted.

#### Remove Edges

Removes selected roof-profile edges from the preview.

Where the same shared edge exists on more than one roof plane, Flow removes the matching copies so they do not continue to affect adjacent mitres.

#### Remove Preview Piece

Allows you to click an unwanted flashing fragment directly in the preview.

Flow identifies the closest source edge and removes the matching preview geometry.

#### Set as Wall Abutment

Adds or reclassifies selected roof edges as wall abutments.

A wall-abutment edge:

- uses the manually added flashing width;
- has no fascia overhang; and
- has no gable downstand.

Use this where the roof meets a wall rather than an exposed fascia or verge.

#### Gable Downstand

Marks selected exposed gable edges for the configured fascia overhang and vertical downstand.

#### Reset Plane

Discards corrections on the selected plane and restores its original automatic result.

#### Navigate View

Temporarily returns control to Revit so you can orbit, zoom or pan the current view.

Press **Esc** to return to the flashing editor.

!!! note

    Revit does not allow changing to another view while an active selection operation is running. Start the workflow in a view that is suitable for both reviewing the preview and selecting the required roof geometry.

### 5. Continue or finish

Select:

- **Confirm & Next** to retain the current plane corrections and select another plane; or
- **Finish** to create the confirmed flashing result.

<!-- SCREENSHOT: Selected roof plane showing a corrected missing edge and a wall-abutment edge in the preview. -->

---

## Existing Flow Flashings

After the roofs are selected, Flow checks for existing Roof Surface Zones associated with those roofs.

If existing flashings are found, choose one of the following options.

### Keep and add

Retains the existing flashings and adds the new result.

Use this when creating additional flashings without replacing earlier work.

### Replace existing

Removes the existing Flow flashings before displaying the new preview.

If the workflow is finished, the existing elements are replaced by the confirmed result.

If the review workflow is cancelled, Flow restores the original flashings.

### Cancel

Stops the workflow without changing the existing flashings.

<!-- SCREENSHOT: Existing Roof Flashings choice showing Keep and add, Replace existing and Cancel. -->

---

## Expected Result

Roof Surface Zones creates separate Generic Model DirectShape elements over the selected roof faces.

The generated geometry:

- follows recognised ridge, hip and gable/verge edges;
- uses the configured widths;
- uses the configured fascia overhang where applicable;
- includes configured gable downstands;
- is raised slightly above the roof surface to improve Revit display; and
- uses the selected material.

Flow-generated elements are identified internally so the tool can detect and replace them during later runs.

The source Revit roof elements remain unchanged.

---

## What Flow Does Automatically

Depending on the selected workflow, Flow automatically:

- collects supported upper roof faces;
- analyses straight roof-profile edges;
- identifies qualifying ridge, hip and gable/verge conditions;
- excludes recognised valley conditions from automatic flashing creation;
- removes matching internal edges between selected associated roof parts;
- resolves supported plan junctions and mitres;
- extends applicable flashing beyond visible fascia edges;
- creates gable-end downstands;
- assigns the selected material;
- previews combined-roof results;
- tracks generated elements against their source roofs; and
- protects existing flashings when a replacement workflow is cancelled.

---

## Tips and Notes

!!! tip "Use automatic mode first"

    For a roof created as one Revit element, start with the normal automatic workflow. It is faster and avoids unnecessary correction steps.

!!! tip "Use combined review for roof assemblies"

    If the physical roof is built from several Revit roof elements, select all associated parts and enable review. Shared junctions and unusual edge classifications can then be checked before creation.

!!! info "Add Edge and Wall Abutment are different"

    **Add Flashing Edge** creates a general flashing edge with standard overhang behaviour.

    **Set as Wall Abutment** creates or reclassifies an edge with no fascia overhang or gable downstand.

!!! note "Check complex roofs visually"

    Roof Surface Zones derives its result from Revit roof-face geometry. Complex junctions should always be checked in plan and 3D before being used for documentation.

---

## Limitations

Roof Surface Zones currently:

- requires planar upper roof faces;
- processes straight roof-profile edges;
- does not automatically create valley flashings;
- creates separate DirectShape geometry rather than native Revit fascia elements or families;
- cannot reliably support native Revit material keynotes on the generated DirectShape faces;
- does not allow changing Revit views during an active selection operation;
- may require manual correction where separate roof elements create ambiguous shared boundaries; and
- may not resolve unusual conditions where a hip or roof plane terminates against an upper-level wall without a usable roof-profile edge.

For a rare unsupported junction, use an appropriate manual Revit modelling or material-based workaround rather than forcing an incorrect generated flashing.

---

## Cancelling

You can cancel from the settings window before roof selection begins.

Pressing **Esc** during roof or edge selection returns to or cancels the relevant editor step.

Selecting **Cancel** in the correction editor removes the temporary preview. If **Replace existing** was chosen, the original Flow flashings are restored.

---

## Troubleshooting

For missing edges, incorrect edge classifications, unexpected mitres, material issues or existing-flashing behaviour, see:

[Roof Tools Troubleshooting](troubleshooting.md)

---

## Related Help

- [Roof Tools](index.md)
- [Roof Outline](roof-outline.md)
- [Gutter Caps](gutter-caps.md)
- [Roof Tools Troubleshooting](troubleshooting.md)

---

<div align="right">
  <a href="#top">🔝 Back to top</a>
</div>
