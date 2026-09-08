# Roof Tools Troubleshooting

Use this page when Roof Outline or Gutter Caps does not produce the expected result.

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

## Related Help

- [Roof Tools](index.md)
- [Roof Outline](roof-outline.md)
- [Gutter Caps](gutter-caps.md)