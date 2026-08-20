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

---

## Merge Filled Regions

Use **Merge Filled Regions** to combine multiple filled regions into one region.

1. Open the **Tools** tab.
2. Select **Merge Filled Regions**.
3. Select at least two filled regions to merge and finish the selection.
4. Select the sample filled region whose type should be applied to the result.

Flow combines the boundaries, creates the merged region using the sampled type, removes the original selected regions and selects the resulting region.

!!! note "The sample controls the result type"

    The regions being merged do not all need to use the same type. The separately sampled filled region determines the type used by the merged result.

---

## Cut Filled Region

Use **Cut Filled Region** to subtract one or more filled regions from a base region.

1. Open the **Tools** tab.
2. Select **Cut Filled Region**.
3. Select the base filled region.
4. Select one or more cutter filled regions and finish the selection.
5. Complete the workflow when prompted.

Flow recreates the base boundary with the cutter areas removed. The cutter regions are deleted when the selected workflow option requires it, and the resulting base region is selected.

The cutter geometry must produce a valid Revit filled-region boundary when subtracted from the base.

---

## Use a Filled Region to Generate a Pattern

A filled region can be selected during **From Geometry** when it contains a usable foreground or background fill pattern.

Flow reads the region’s fill grids directly. It does not treat the filled-region boundary as pattern linework.

This is useful when a pattern already exists graphically in the project and needs to be opened as an editable Pattern Manager definition.

See [**Generating Patterns from Geometry**](generating-patterns-from-geometry.md).

---

## Cancel an Operation

Press **Esc** during a Revit selection or boundary capture to cancel. Pattern Manager reappears without applying the operation.

---

## Acknowledgement

The filled-region utilities are Flow’s native implementation of useful workflows demonstrated by the pyRevit community and are integrated with Flow’s project-pattern and profile-capture systems.

---

## Related Help

- [Pattern Manager](index.md)
- [Project Patterns](project-patterns.md)
- [Generating Patterns from Geometry](generating-patterns-from-geometry.md)
- [Troubleshooting](troubleshooting.md)