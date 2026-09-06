# Roof Outline

**Roof Outline** creates a clean 2D outline around the outside perimeter
of one or more Revit footprint roofs.

It is useful when a roof plan needs a clear documentation line around
the overall roof form without showing the internal footprint edges
created where separate roof elements meet.

---

## Opening the Tool

On the Revit ribbon:

**Flow → Model → Roof Tools → Roof Outline**

---

## Before You Start

Open the plan view in which the roof outline is required.

!!! note "Supported roof type"

    Roof Outline currently uses the footprint profiles of Revit **Roof by Footprint** elements.

    Other roof creation methods are not currently supported by this workflow.

---

## Creating a Roof Outline

1. Open the required plan view.
2. Open **Flow → \[VERIFY PANEL NAME\] → Roof Tools**.
3. Choose **Roof Outline**.
4. Select one or more Revit roofs when prompted.
5. Finish the Revit selection.
6. Review the outline created in the active plan view.

Flow creates detail lines around the exterior perimeter of the combined
selected roof geometry.

!!! info "What Flow does automatically"

    Flow reads the footprint profiles of the selected roofs, removes coincident edges shared by adjoining roof elements and determines the outside boundary of the combined roof geometry.

    Concave changes in the outside perimeter are retained while internal roof junction lines are excluded from the final outline.

---

## Existing Roof Outlines

When the option to delete an existing outline is enabled, Flow removes
existing detail curves in the active view that use the dedicated Roof
Outline line style before creating the new result.

This allows the outline to be regenerated after the roof design changes.

---

## What Flow Creates

Roof Outline creates **2D detail curves** in the active plan view.

It does not alter the selected Revit roof elements.

The resulting curves use the dedicated Flow roof outline line style so
they can be controlled consistently in the project.

---

## Checking the Result

After creating the outline, check that:

- the line follows the full outside perimeter of the intended roof;
- internal junctions between adjoining selected roofs are not shown;
- concave steps and recesses in the roof perimeter are retained; and
- the correct roof elements were included in the selection.

For unusual or highly complex roof arrangements, visually check the
generated perimeter before relying on it for documentation.

---

## Cancelling

Press **Esc** while selecting roofs to cancel the selection workflow.

No new roof outline is created when the selection is cancelled.

---

## Related Help

- [Roof Tools](index.md)
- [Roof Tools Troubleshooting](troubleshooting.md)