# Wall Dimensions

**Wall Dimensions** creates coordinated dimensions for walls in a plan view using Flow dimensioning rules.

The workflow is intended for quickly generating consistent wall dimensions where dimension control lines have been placed through the walls that need to be documented.

------------------------------------------------------------------------

## Opening the Tool

On the **Flow** ribbon:

1.  Open **Annotation**.
2.  Choose **Wall Dimensions**.

------------------------------------------------------------------------

## Before You Start

Use the tool from a supported plan view.

Prepare the model lines that identify where the wall dimensions are to be created. The dimensioning workflow uses those lines to find relevant walls and establish the resulting dimension line.

!!! note "Plan workflow"

    Wall Dimensions is intended for **Floor Plan** and **Reflected Ceiling Plan** views.

------------------------------------------------------------------------

## Creating Wall Dimensions

1.  Open the required plan view.
2.  Select the required model lines before opening the tool, or start **Wall Dimensions** and select them when prompted.
3.  If selecting after launch, use a crossing selection where convenient.
4.  Complete the selection.
5.  Flow finds walls associated with the selected model lines.
6.  Flow creates coordinated dimensions for compatible wall groups.

Where a selected line crosses or touches multiple parallel walls, Flow groups compatible walls and creates a continuous dimension string from the wall references it can resolve.

------------------------------------------------------------------------

## What Flow Does Automatically

The source workflow identifies walls in the active view and groups parallel walls together before dimensioning them.

It uses wall core information to establish dimension references and creates the resulting dimension along the selected model line.

The historical workflow also creates supporting hidden detail references and locked dimensions as part of resolving wall core locations.

!!! info "Model lines are working geometry"

    The source workflow removes a model line after a dimension has been created successfully from it.

------------------------------------------------------------------------

## If Some Walls Are Not Dimensioned

A wall may be skipped where Flow cannot resolve suitable geometry or dimension references.

Common causes include:

-   the model line does not intersect or pass sufficiently close to the wall;
-   the wall is on a different level from the active plan;
-   wall compound/core information cannot be resolved;
-   fewer than two usable references are available for a dimension string;
-   the selected walls do not form a compatible parallel group.

See [Wall Dimensions Troubleshooting](troubleshooting.md).

------------------------------------------------------------------------

## Related Help

-   [Annotation](index.md)
-   [Grid Dimensions](grid-dimensions.md)
-   [Join Dimensions](join-dimensions.md)