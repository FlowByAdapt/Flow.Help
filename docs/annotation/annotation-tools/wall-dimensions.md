# Wall Dimensions

**Wall Dimensions** creates coordinated wall-core dimensions by drawing a dimension path through the walls that need to be documented.

Flow finds suitable walls along the path, resolves their core boundaries and creates a continuous dimension string at the location you choose.

No Model Lines or other control geometry need to be prepared before starting the tool.

**Ribbon:** **Flow → Annotation → Wall Dimensions**

---

## When to Use Wall Dimensions

Use **Wall Dimensions** when you need to quickly dimension a series of straight walls in plan.

The workflow is particularly useful for:

* dimensioning multiple parallel walls with a single dimension string;
* documenting wall core locations consistently;
* placing coordinated internal or external wall dimensions;
* creating several wall dimension strings without repeatedly restarting the tool.

---

## Before You Start

Wall Dimensions can be used in:

* **Floor Plans**
* **Reflected Ceiling Plans**

The walls to be dimensioned should be straight and visible in the active view.

Where the plan is associated with a level, Flow looks for walls hosted on that level.

!!! note "No control lines required"

	You do not need to draw or select Model Lines before starting Wall Dimensions.

	The dimension path is drawn interactively while the tool is running.

---

## Creating Wall Dimensions

### 1. Pick the Path Start

Start:

**Flow → Annotation → Wall Dimensions**

Flow prompts:

> Pick the start point of the dimension path. Press Escape to finish.

Click to establish the start of the path.

### 2. Draw the Dimension Path

Move the cursor through the walls that need to be dimensioned.

Flow displays a live preview of the dimension path.

The path determines which walls Flow will investigate for dimensioning.

Click again to accept the path.

<!-- Screenshot recommended:
Show the live dimension-path preview crossing several parallel walls.
-->

!!! tip "Constrain the path"

	Flow normally assists with constraining the dimension path based on the walls in the active plan.

	Hold **Ctrl** while positioning the path to constrain it horizontally or vertically instead.

### 3. Pick the Dimension Line Location

After accepting the path, Flow prompts:

> Pick the dimension line location.

Click where you want the resulting dimension string to appear.

The dimension remains parallel to the path you drew but is moved to the selected location.

<!-- Screenshot recommended:
Show the established path and the user selecting the final dimension-line location.
-->

### 4. Continue or Finish

If the dimension is created successfully, Flow immediately prompts for the start of another dimension path.

Repeat the process to create additional wall dimensions.

Press **Esc** when you have finished.

---

## How Wall Dimensions Finds Walls

Flow uses the dimension path to identify suitable walls in the active view.

A wall can be considered where its location passes through the path or where the path passes sufficiently close to it.

Flow then filters the discovered walls so that only suitable walls are used for the dimension.

For the current workflow:

* the wall must be visible in the active view;
* the wall must be straight;
* the wall must be perpendicular to the dimension path;
* where the view has an associated level, the wall must be hosted on that level;
* Flow must be able to resolve usable wall-core information.

!!! tip "Draw across the walls"

	For predictable results, draw the dimension path across the walls you want to dimension rather than along them.

	A path drawn perpendicular to a series of parallel walls allows Flow to resolve those walls as a coordinated dimension set.

---

## What Flow Dimensions

Wall Dimensions uses the **core boundaries** of compatible walls rather than simply dimensioning their wall centre lines.

For each suitable wall, Flow resolves its interior and exterior core locations and uses those positions to construct the resulting dimension chain.

This allows a single path through several walls to produce a coordinated continuous dimension string.

!!! note "Wall construction matters"

	Flow relies on usable wall compound and core information.

	Walls whose core locations cannot be resolved may be omitted from the resulting dimension.

---

## Supporting References

Revit does not always provide suitable direct references at the calculated wall-core positions.

To support these dimensions, Flow creates and manages small supporting references at the required core locations. These references are constrained back to the source walls and are used to create the final dimension.

Flow attempts to keep the supporting geometry out of the way by using hidden references and hidden supporting constraints.

The final wall dimension is also locked where Revit permits it.

!!! info "Managed by Flow"

	Supporting references created by Wall Dimensions are managed as part of the Flow dimension set.

	When Wall Dimensions is started, Flow checks the active view and removes orphaned Flow wall-dimension references where the source wall or final dimension no longer exists.

	These supporting references do not need to be created or maintained manually.

---

## If a Wall Is Not Dimensioned

A wall may be skipped if Flow cannot resolve suitable geometry or wall-core references.

Common causes include:

* the dimension path does not cross or pass sufficiently close to the wall;
* the wall is not perpendicular to the dimension path;
* the wall is curved rather than straight;
* the wall is hosted on a different level from the active plan;
* suitable wall compound or core information cannot be resolved;
* there are not enough usable references to create the dimension.

At least two usable references are required to create a dimension.

If Flow cannot create a valid dimension from the path, no incomplete dimension set is retained.

See [Wall Dimensions Troubleshooting](troubleshooting.md).

---

## Dimension References

When several wall-core references coincide or would produce a zero-length dimension segment, Flow attempts to remove the redundant reference before creating the final dimension.

This helps prevent duplicate core positions from producing invalid dimension segments.

---

## Related Help

* [Annotation](index.md)
* [Grid Dimensions](grid-dimensions.md)
* [Join Dimensions](join-dimensions.md)