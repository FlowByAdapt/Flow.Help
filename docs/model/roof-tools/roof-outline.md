# Roof Outline

Roof Outline creates a clean 2D outline around the outside perimeter of one or more Revit **Roof by Footprint** elements.

It is particularly useful where several roof elements form a single overall roof and the required documentation should show the exterior roof perimeter without the junctions between individual roofs.

## Open Roof Outline

1. Open the plan view where the outline is required.
2. Go to **Flow → Model → Roof**.
3. Select **Roof Outline**.

The Roof window closes and Revit prompts you to select the roofs to outline.

## Before You Start

Roof Outline must be run from a **plan view**.

The current implementation supports Revit **Roof by Footprint** elements. Other Revit roof creation methods are not currently supported.

For the best result, select all Roof by Footprint elements that contribute to the exterior perimeter you want Flow to generate.

## Create a Roof Outline

1. Open the required plan view.
2. Go to **Flow → Model → Roof**.
3. Select **Roof Outline**.
4. Select one or more Roof by Footprint elements in Revit.
5. Click **Finish** to complete the Revit selection.
6. Flow analyses the selected roof footprints and creates the exterior outline.
7. Review the resulting Detail Lines against the roof geometry.

<!-- SCREENSHOT: Before/after plan showing several adjoining footprint roofs and the resulting exterior Roof_Outline. Ideally include an internal roof junction and a non-rectangular or concave part of the perimeter. -->

## What Flow Does Automatically

When Roof Outline runs, Flow:

* reads the footprint profiles of the selected roofs;
* combines their profile geometry;
* removes coincident shared edges;
* splits intersecting boundary geometry where required;
* determines the exterior boundary of the combined roof shape;
* removes unnecessary backtracking and collinear points;
* removes an existing `Roof_Outline` from the active view;
* creates the new exterior perimeter as Detail Lines; and
* restores the original view settings when processing is complete.

The generated lines are projected onto the level associated with the active plan view.

## Existing Roof Outlines

Before creating the new outline, Flow removes existing Detail Lines in the **active view** that use the `Roof_Outline` line style.

This allows the command to be rerun when the roof design changes without leaving the previous generated outline behind.

!!! warning

	Existing outline lines are identified by their `Roof_Outline` line style. Manually created Detail Lines using the same line style in the active view may therefore also be removed when Roof Outline is rerun.

## Roof Outline Line Style

Flow uses a dedicated line style named:

`Roof_Outline`

If the line style does not exist, Flow creates it automatically.

The style uses projection line weight **1**. Where the `ADa_Dash5` line pattern is available in the project, Flow assigns that pattern to the line style.

The absence of `ADa_Dash5` does not prevent the roof outline from being created.

## Temporary View Changes

Roof Outline temporarily adjusts the active plan so the roof geometry can be processed.

Where required, Flow temporarily removes the assigned View Template and adjusts the View Range.

The original View Template and View Range are restored automatically after processing, including when roof selection is cancelled.

!!! info

	These temporary changes are part of the processing workflow. You do not need to manually change the View Template or View Range before running Roof Outline.

## Selecting Multiple Roofs

Multiple Roof by Footprint elements can be selected in a single operation.

This is useful where separate roof elements meet to form one overall roof.

Flow removes matching shared edges and analyses the remaining boundary geometry to determine the exterior perimeter.

For this reason, select **all roofs that contribute to the intended combined outline**.

## Checking the Result

After Roof Outline finishes, check that:

* the outline follows the required exterior roof perimeter;
* shared junctions between adjoining roofs have been removed;
* external corners and changes in direction have been retained; and
* the resulting Detail Lines are suitable for the intended documentation.

The generated outline is 2D view-specific documentation. Roof Outline does **not** modify the selected roof elements.

## Cancelling

Press **Esc** while selecting roofs to cancel the operation.

No new outline is created and the original view settings are restored.

## Limitations

Roof Outline currently:

* must be run from a plan view;
* supports Roof by Footprint elements;
* creates view-specific Detail Lines rather than model geometry;
* determines the exterior boundary from the selected footprint profiles; and
* identifies previous generated outline lines by the `Roof_Outline` line style rather than separate element provenance.

Complex or unusual footprint arrangements should be checked visually after the command completes.

## Related Help

* [Roof Tools](index.md)
* [Gutter Caps](gutter-caps.md)
* [Roof Tools Troubleshooting](troubleshooting.md)
