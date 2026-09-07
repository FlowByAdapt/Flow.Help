# Roof Tools Troubleshooting

Use this page when Roof Outline or Gutter Caps does not produce the expected result.

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

* confirm that all roofs contributing to the required perimeter were selected;
* check whether an unrelated roof was included accidentally;
* check the roof footprint geometry for unusual intersections or overlaps; and
* compare the generated Detail Lines with the roof geometry.

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

## Gutter Caps — Invalid Element Selected

Gutter Caps operates on Revit **Gutter** elements.

If the required gutter is difficult to select, use **Tab** to cycle through nearby Revit elements until the gutter is highlighted.

## Gutter End Cannot Be Found

Pick closer to the physical end of the gutter.

The established workflow searches for a suitable gutter-end face nearest the picked point. Picking too far from the end can prevent the correct geometry from being identified.

## A Gutter Cap Was Not Created

The selected end may already have a generated Gutter Cap.

The established workflow checks for an existing cap near the selected end and skips creation when a duplicate is detected.

If no cap is visible, inspect the end closely in a suitable 3D view before trying again.

## The Gutter Cap Shape Is Unexpected

The cap geometry is derived from the gutter's end profile.

Complex or unusual gutter profiles may produce geometry that needs additional checking.

The generated cap is a separate element, so the original Revit gutter remains unchanged.

## How Do I Finish Gutter Caps?

Press **Esc** after processing the required ends of the selected gutter.

The established workflow then selects the newly created caps and brings them into view for review.

## Related Help

* [Roof Tools](index.md)
* [Roof Outline](roof-outline.md)
* [Gutter Caps](gutter-caps.md)
