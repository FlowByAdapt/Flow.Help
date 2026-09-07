# Filled Region Tools

Pattern Manager includes tools for creating, merging and cutting Revit filled regions, as well as using an existing filled-region pattern as input to **From Geometry**.

---

## Supported Views

Merge and Cut are available in supported graphical views, including:

- floor and ceiling plans;
- engineering and area plans;
- sections and details;
- elevations; and
- drafting views.

The operation is stopped with a message when the active view type is not supported.

---

## Create a Filled Region from a Project Pattern

1. Open **Project Patterns**.
2. Right-click the pattern to use.
3. Select **Create Filled Region**.
4. Choose how to define the boundary:
   - **Draw Boundary**; or
   - **Use Linework**.
5. Complete the boundary capture in Revit.

Flow creates a filled-region type using the selected pattern where required, creates the region from the captured loops and selects the completed region.

The boundary must form valid closed loops suitable for a Revit filled region.

### Draw Boundary

Pick at least three points. Revit snapping is available for endpoints, intersections, midpoints and nearest points. Press **Esc** after the final point and Flow closes the last segment back to the first point automatically.

This mode creates straight boundary segments and one closed loop. Temporary detail-line previews are removed after the region is created.

### Use Linework

Select detail or model CurveElements that form one or more closed loops, then click **Finish**. Flow orders and reverses connected curves where necessary.

!!! warning "Selected source linework is removed"

    After the filled region is created successfully, Flow deletes the selected source CurveElements. Copy important linework first if it must remain in the view.

Flow reuses a filled-region type whose foreground pattern matches the selected project pattern. If none exists, it creates or updates a type named `Flow - [pattern name]`. At least one filled-region type must already exist in the project for Flow to duplicate when a new type is required.

---

## Merge Filled Regions

Use **Merge Filled Regions** to combine multiple filled regions into one region.

1. Open the **Tools** tab.
2. Select **Merge Filled Regions**.
3. Select at least two filled regions to merge and finish the selection.
4. Select the sample filled region whose type should be applied to the result.

Flow combines the boundaries, creates the merged region using the sampled type, removes the original selected regions and selects the resulting region.

<!-- SCREENSHOT: Before-and-after Revit views showing several source regions and the single merged result. -->

!!! note "The sample controls the result type"

    The regions being merged do not all need to use the same type. The separately sampled filled region determines the type used by the merged result.

All selected and sampled regions must belong to the active view. The sample may also be one of the regions selected for merging.

---

## Cut Filled Region

Use **Cut Filled Region** to subtract one or more filled regions from a base region.

1. Open the **Tools** tab.
2. Select **Cut Filled Region**.
3. Select the base filled region.
4. Choose **Delete Cutters** or **Keep Cutters**.
5. Select one or more cutter filled regions and click **Finish**.

Flow creates a replacement region using the base region's type, removes the original base region and selects the result.

- **Keep Cutters** retains the selected cutter regions.
- **Delete Cutters** removes every selected cutter region after a successful cut, including any selected cutter that did not overlap the base.

Cutters that do not overlap the base are ignored during the subtraction. At least one selected cutter must remove part of the base region.

The cutter geometry must produce a valid Revit filled-region boundary when subtracted from the base.

<!-- SCREENSHOT: Before-and-after Revit views showing the base, cutters and completed cut result. -->

---

## Use a Filled Region to Generate a Pattern

A filled region can be selected during **From Geometry** when it contains a usable foreground or background fill pattern.

Flow reads the region’s fill grids directly. It does not treat the filled-region boundary as pattern linework.

This is useful when a pattern already exists graphically in the project and needs to be opened as an editable Pattern Manager definition.

See [**Generating Patterns from Geometry**](generating-patterns-from-geometry.md).

---

## Cancel an Operation

Press **Esc** during a Revit selection to cancel. When drawing a boundary, **Esc** before the first point cancels; after points have been placed it finishes point capture and Flow attempts to close the loop. Pattern Manager then reappears.

---

## Acknowledgement

The filled-region utilities are Flow’s native implementation of useful workflows demonstrated by the pyRevit community and are integrated with Flow’s project-pattern and profile-capture systems.

---

## Related Help

- [Pattern Manager](index.md)
- [Project Patterns](project-patterns.md)
- [Generating Patterns from Geometry](generating-patterns-from-geometry.md)
- [Troubleshooting](troubleshooting.md)