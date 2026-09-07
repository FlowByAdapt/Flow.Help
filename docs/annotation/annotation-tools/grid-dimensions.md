# Grid Dimensions

**Grid Dimensions** creates coordinated dimension strings for selected grids in the active Revit view.

Flow automatically identifies parallel grid groups, excludes grids that are already dimensioned and lets you place each dimension string directly in the view.

**Ribbon:** **Flow → Annotation → Grid Dimensions**

---

## When to Use Grid Dimensions

Use **Grid Dimensions** when you need to quickly create continuous dimensions across groups of parallel grids.

Rather than dimensioning each grid set separately, Flow can:

* identify parallel grid groups automatically
* process multiple grid orientations from the same selection
* exclude grids already referenced by dimensions
* apply a consistent Dimension Type
* let you choose the location of each resulting dimension string

---

## Supported Views

Grid Dimensions can be used in:

* **Floor Plans**
* **Reflected Ceiling Plans**
* **Engineering Plans**
* **Area Plans**
* **Sections**
* **Elevations**
* **Detail Views**

Other view types are not supported.

---

## Before You Start

Open the Revit view containing the grids you want to dimension.

Grid Dimensions works with **straight grids** that form parallel groups.

Each usable group must contain at least **two grids**.

The project must also contain at least one linear Dimension Type whose name begins with `ADa`.

!!! tip "Preselection is supported"

	You can select two or more grids before starting Grid Dimensions.

	Flow uses those preselected grids for the first dimensioning operation.

---

## Creating Grid Dimensions

### 1. Select the Grids

Start:

**Flow → Annotation → Grid Dimensions**

If at least two grids were preselected before opening the tool, Flow uses that selection automatically.

Otherwise, Revit prompts you to:

**Select the grids to dimension. Press Escape to finish.**

Select the required grids and complete the Revit selection.

You can include grids running in different directions in the same selection. Flow separates them into usable parallel groups automatically.

<!-- Screenshot recommended:
Show a plan containing grids in two different directions with both sets selected.
This demonstrates that multiple grid orientations can be included in one selection.
-->

### 2. Flow Checks Existing Dimensions

Flow checks whether any of the selected grids are already referenced by dimensions in the active view.

Already-dimensioned grids are excluded.

If any are found, Flow reports the number of excluded grids and lists their Grid Names.

!!! info "Existing grid dimensions are protected"

	A grid is considered already dimensioned when it is referenced by an existing dimension in the active view.

	It does not matter which Dimension Type was used or whether the existing dimension was created by Flow.

If fewer than two undimensioned grids remain after filtering, Flow asks you to make another grid selection.

### 3. Flow Groups the Grids

The remaining grids are grouped automatically according to their direction in the active view.

Each parallel group containing at least two usable straight grids can produce a dimension string.

There is no need to specify whether the grids are vertical, horizontal or angled.

!!! info "Mixed grid directions"

	A single selection can contain multiple grid directions.

	For example, Flow can identify one group running in one direction and another group running perpendicular or at an angle to it. Each usable group is dimensioned separately.

### 4. Choose the Dimension Type

The first time a usable grid group is found, Flow opens the **Choose the dimension type** window.

Only linear Dimension Types whose names begin with `ADa` are available.

If `ADa_Blue` exists, Flow places it first in the list.

Choose the required Dimension Type and select **Continue**.

<!-- Screenshot recommended:
Show the Grid Dimensions "Choose the dimension type" window with several ADa Dimension Types visible and ADa_Blue first, if available.
-->

!!! note "Dimension Type is retained"

	Your selected Dimension Type is used for each parallel grid group and subsequent grid selections during the current Grid Dimensions run.

	You do not need to select it again for each group.

### 5. Place the Dimension

For each parallel grid group, Revit prompts you to pick the dimension location.

Click where you want the dimension string to be placed.

<!-- Screenshot recommended:
Show the active Revit view while Flow is prompting for the dimension location.
The relevant grid group should be clearly visible.
This demonstrates the click-to-place workflow.
-->

Flow automatically:

* determines the grid direction
* creates a dimension direction perpendicular to the grids
* orders the grid references correctly
* creates the continuous dimension string using the selected Dimension Type

You control the dimension's location by clicking directly in the view.

### 6. Continue Dimensioning

If your selection contains more than one usable parallel group, Flow prompts you to place each group in turn.

After all groups from the current selection have been processed, Flow returns to grid selection.

You can then select another set of grids and continue using the same Dimension Type.

Press **Esc** when you have finished.

---

## Parallel Grid Groups

Grid Dimensions automatically identifies grids that are parallel in the active view.

This means you do not need separate workflows for vertical, horizontal or angled grids.

For example, a selection containing:

* several parallel grids running in one direction; and
* several parallel grids running in another direction

can be separated into two dimension groups automatically.

Groups containing fewer than two usable grids cannot create a dimension.

Curved grids are not currently supported by this workflow.

---

## Existing Grid Dimensions

Grid Dimensions avoids creating additional dimensions for grids that are already dimensioned in the active view.

Flow checks existing dimensions in that view and identifies the grids they reference.

If a selected grid is already referenced:

1. the grid is excluded from the new dimension
2. Flow reports that it has been excluded
3. the existing dimension remains unchanged

If fewer than two usable grids remain, no new dimension is created for that selection.

!!! note "Active view"

	Existing-dimension checking applies to dimensions in the active view.

	A grid referenced by a dimension in another view does not prevent it from being dimensioned in the current view.

---

## Dimension Type

Grid Dimensions uses a standard linear Revit Dimension Type selected during the workflow.

The chooser includes Dimension Types that:

* use the **Linear** dimension style; and
* have a name beginning with `ADa`.

`ADa_Blue` is placed first when it is available.

If no suitable `ADa` linear Dimension Types exist, Flow reports:

**No ADa linear dimension types are available in this project.**

Load or create an appropriate Dimension Type before running Grid Dimensions again.

---

## Dimension Placement

Dimension placement is controlled directly in the Revit view.

For each parallel group, click the location where you want the dimension string.

Flow uses this point to establish the dimension baseline and automatically determines the correct dimension direction relative to the grids.

This works for horizontal, vertical and angled parallel grid arrangements without requiring a separate orientation setting.

<!-- Screenshot recommended:
Show the completed result using the same grid arrangement as the earlier selection screenshot.
Include dimension strings for two different parallel groups.
-->

---

## Duplicate and Zero-Length Segments

When creating the dimension string, Flow protects against references that would result in zero-length dimension segments.

If a zero-length segment is encountered, Flow can remove the redundant reference and retry the dimension creation.

This helps produce a valid continuous dimension where the remaining grid references allow it.

---

## If a Grid Dimension Cannot Be Created

### Fewer than two grids selected

Grid Dimensions requires at least two grids.

If necessary, Flow prompts you to select additional grids.

### Grids are already dimensioned

Already-dimensioned grids are excluded automatically.

If fewer than two undimensioned grids remain after filtering, Flow cannot create a dimension from that selection.

Select another grid group or review the existing dimensions in the active view.

### No usable parallel group

If the remaining selection does not contain at least two usable straight parallel grids, Flow reports:

**Flow could not find a parallel group containing at least two usable straight grids.**

Check that the selected grids are straight and that at least two run parallel to each other.

### No suitable Dimension Type

The project must contain at least one linear Dimension Type beginning with `ADa`.

If none are available, load or create the required Dimension Type and run Grid Dimensions again.

### Revit cannot create the dimension

If an individual grid group cannot be dimensioned, Flow reports the failure and continues with the workflow where possible.

Review the grid geometry and selected dimension location before trying again.

---

## Related Help

* [Grid Dimensions Troubleshooting](troubleshooting.md)
* [Annotation](index.md)
* [Wall Dimensions](wall-dimensions.md)
* [Join Dimensions](join-dimensions.md)