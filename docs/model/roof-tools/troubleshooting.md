# Roof Tools Troubleshooting

Use this page when Roof Surface Zones, Roof Outline or Gutter Caps does not produce the expected result.

---

## Roof Outline Cannot Be Run

**Message:** `Roof Outline can only be run from a plan view.`

Roof Outline must be started from a Revit plan view.

Open the plan where the roof outline is required, then run:

**Flow → Model → Roof → Roof Outline**

## No Revit Roofs Were Selected

Roof Outline ignores selected elements that are not Revit roofs.

Run the command again and select one or more Revit roof elements before clicking **Finish**.

## No Roof Footprint Profile Curves Were Found

The current Roof Outline implementation supports Revit **Roof by Footprint** elements.

Other Revit roof creation methods do not currently provide the footprint information required by this workflow.

Use Roof Outline with Roof by Footprint elements.

## The Exterior Boundary Could Not Be Determined

Flow combines the selected roof footprint profiles and analyses the resulting geometry to determine the exterior boundary.

If an exterior boundary cannot be determined:

1. Check that the required Roof by Footprint elements were selected.
2. Make sure all roofs contributing to the intended overall perimeter were included.
3. Check the roof footprints for unusual, disconnected or overlapping geometry.
4. Run Roof Outline again.

## The Roof Outline Is Not What I Expected

Roof Outline treats the selected roof footprints as a combined boundary network.

If the result is unexpected:

- confirm that all roofs contributing to the required perimeter were selected;
- check whether an unrelated roof was included accidentally;
- check the roof footprint geometry for unusual intersections or overlaps; and
- compare the generated Detail Lines with the roof geometry.

Complex arrangements should always be visually checked after generation.

## My Existing Roof Outline Disappeared

This is expected when Roof Outline is rerun.

Before creating the new outline, Flow removes existing Detail Lines in the active view that use the `Roof_Outline` line style.

!!! warning

    This is based on the line style rather than separate generated-element provenance. Manually created Detail Lines using `Roof_Outline` in the active view may therefore also be removed.

## The Roof Outline Has the Wrong Line Pattern

Flow uses the `Roof_Outline` line style and looks for the `ADa_Dash5` line pattern.

If `ADa_Dash5` exists, it is assigned to the Roof Outline style. If it is unavailable, Flow can still create the outline but cannot apply that pattern automatically.

## My View Template or View Range Changed

Roof Outline temporarily changes the active plan's view settings while processing the roof geometry.

The original View Template and View Range should be restored automatically when the operation finishes or roof selection is cancelled.

If the view does not return to its previous state after an unexpected failure, review the View Template and View Range manually.

---

## Gutter Caps Cannot Find a Roof Plan

**Message:** `Gutter Caps requires a roof plan view. No suitable Roof Plan view could be found.`

Gutter Caps requires a non-template plan view whose name contains:

**Roof Plan**

If you are not already in a matching view, Flow searches the project and switches automatically.

If no suitable view exists, create or rename the required Roof Plan and run Gutter Caps again.

## I Can't Select the Gutter

Gutter Caps only accepts Revit **Gutter** elements during the gutter-selection step.

If the gutter is difficult to highlight, use **Tab** to cycle through nearby roof elements until the gutter is highlighted, then click to select it.

You can also preselect exactly one gutter before starting Gutter Caps.

## Gutter Caps Used the Wrong End

Flow uses the suitable gutter end nearest to the point you click.

If the wrong end is processed, run the tool again and click much closer to the physical end you intend to cap.

## A Gutter Cap Was Not Created

The selected end may already have a recognised generated Gutter Cap.

Flow checks for an existing cap near the selected end and skips creation when a duplicate is detected.

Review the completion summary. If **Skipped existing** increased, inspect the gutter end closely before trying again.

## The Gutter Cap Shape Is Unexpected

The cap geometry is derived from the actual gutter-end profile.

Complex or unusual gutter profiles can require additional visual checking.

Inspect the result in a suitable 3D view. If the generated profile is clearly incorrect, remove the generated cap and report the gutter type/profile used.

## I Can See a Line Between the Gutter and Cap

The generated cap is a separate DirectShape element. It is not geometrically joined to the native Revit gutter.

A visible junction or internal edge can therefore remain between the gutter and cap in some model or 3D display conditions.

This does not necessarily indicate that the cap geometry is incorrect.

## The Cap Is a Generic Model

Flow first attempts to create the generated DirectShape using the Revit **Gutter** category.

Where Revit does not permit that category for the generated geometry, Flow falls back to **Generic Models**.

This is expected fallback behaviour.

## The Cap Material Does Not Match

Flow attempts to resolve and apply a matching gutter material to each generated cap.

If no usable material can be resolved, the cap can still be created. The completion summary reports how many newly created caps received a material.

## How Do I Finish Gutter Caps?

Press **Esc** after processing the required ends of the selected gutter.

During end picking, Esc finishes the current run. Caps already created are retained.

Flow then selects the newly created caps, attempts to bring them into view and displays the completion summary.

To cap a different gutter, start Gutter Caps again.

---

## Roof Surface Zones Cannot Find the Material

**Message:** `The material '…' was not found in this project.`

The material name entered in Roof Surface Zones must match a material that already exists in the current Revit project.

Check the spelling and punctuation of the material name. The default is:

`*ROF.SHEET_Flashing`

Create or load the required material, or enter the name of another suitable project material.

## No Qualifying Flashing Edges Were Found

Flow creates automatic flashing only on recognised ridge, hip and gable/verge conditions.

Check that:

1. At least one flashing type is enabled.
2. The selected roof contains planar upper faces.
3. The required boundaries are straight roof-profile edges.
4. All associated roof parts were selected where combined analysis is enabled.

Valleys and horizontal eave boundaries are not automatically treated as flashing edges.

## A Flashing Edge Is Missing

For a roof made from several elements:

1. Enable **Analyse associated roof parts together**.
2. Enable **Review and correct combined result**.
3. Select every roof element contributing to the physical roof.
4. Select the affected roof plane.
5. Use **Add Flashing Edge** on the omitted roof-profile edge.

The added flashing uses the **Manually added flashing width**.

If Revit does not expose a usable roof-profile edge at an unusual wall or upper-roof junction, the condition may not be correctable through the editor. Use an appropriate manual Revit modelling or material-based workaround.

## An Incorrect Flashing Edge Was Created

Select the affected roof plane in combined review, then use:

- **Remove Edges** when the source roof-profile edge can be selected; or
- **Remove Preview Piece** when it is easier to click the unwanted flashing fragment directly.

Use **Reset Plane** if you need to discard the plane corrections and return to the automatic result.

## A Wall Edge Has Fascia Overhang or a Gable Downstand

The edge may have been classified as an exposed gable or fascia condition.

During combined review:

1. Select the affected roof plane.
2. Select **Set as Wall Abutment**.
3. Select the roof-profile edge meeting the wall.
4. Finish the Revit selection.

A wall-abutment edge has no fascia overhang or gable downstand.

## The Gable End Is Open

Select the affected roof plane, choose **Gable Downstand**, and select the exposed gable edge.

The result uses the configured fascia overhang and gable downstand depth.

## The Flashing Mitre Is Unexpected

Roof Surface Zones derives mitres from the detected roof-face and roof-profile geometry.

Check that:

- all associated roof parts were included;
- incorrect valley or shared edges have been removed;
- wall-abutment edges are classified correctly; and
- the source Revit roof and wall junctions meet cleanly in plan.

Some unusual junctions, particularly where a hip or roof plane terminates against an upper-level wall without a usable roof-profile edge, may require a manual modelling workaround.

## Existing and New Flashings Are Both Visible

When existing Flow flashings are detected, select **Replace existing** before entering the preview editor.

Flow removes the existing generated flashings while the replacement is reviewed. Cancelling the workflow restores the originals.

Choose **Keep and add** only when both the existing and newly created flashings are required.

## I Cannot Change Revit Views While Editing

Revit does not allow changing views while an active selection operation is running.

Use **Navigate View** to orbit, pan or zoom the current view. Press **Esc** to return to the editor.

If another view is required, cancel the workflow, open the required view and run Roof Surface Zones again.

## Material Keynotes Cannot Select the Flashing

Roof Surface Zones creates Generic Model DirectShape geometry. Although the selected material controls appearance, Revit cannot reliably attach a native material keynote to the generated tessellated faces.

Use a suitable user-keynote or manual annotation workflow where the flashing must be referenced in documentation.

## Lines Appear Through the Flashing

The generated flashing is raised slightly above the roof surface to reduce Revit display-line interference.

If lines are visible only at particular zoom levels, this may be a Revit display effect rather than incorrect geometry. Check the result at the intended documentation scale and in a suitable plan or 3D view.

---

## Related Help

- [Roof Tools](index.md)
- [Roof Surface Zones](roof-surface-zones.md)
- [Roof Outline](roof-outline.md)
- [Gutter Caps](gutter-caps.md)