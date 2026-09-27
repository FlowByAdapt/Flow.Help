# Separating Walls

Wall Manager converts each selected supported compound wall into coordinated output walls based on the layer groups shown in the window.

---

## Select Walls

You can select walls before opening Wall Manager or update the working set while it remains open.

1. Select the required walls in Revit.
2. Choose **Add selected**.
3. Repeat as required.

Multiple wall instances and multiple compatible wall types can be included in one working set. Each wall type is listed separately so its layer configuration can be reviewed.

Use **Remove selected** to remove only the walls currently selected in Revit. Use **Clear** to empty the entire working set.

---

## Review the Wall Preview

Select a wall type in the left grid to display its assembly.

The preview identifies:

- exterior and interior orientation;
- the physical source layers;
- current output groups; and
- the proposed host layer.

Review the orientation before continuing, particularly where the source wall direction varies.

---

## Configure Output Groups

Each physical source layer initially becomes an individual output wall.

To combine layers:

1. Hold **Ctrl**.
2. Select two or more adjacent source layers.
3. Choose **Combine selected**.
4. Rename the output group if a clearer wall-type name is required.

Only adjacent layers can be combined. Use **Separate all layers** to reset the selected wall type to one output wall per physical layer.

Wall Manager creates unique wall-type names where required so repeated runs do not conflict with existing generated types.

---

## Select the Host Wall

If selected source walls contain doors or windows:

1. Select the required proposed output wall.
2. Choose **Set selected as host**.
3. Confirm that the host indicator appears on the intended group.

The host should normally be the layer intended to control and cut the opening.

---

## Review Warnings

Resolve blocking warnings before running the separation. Typical checks include:

- unsupported wall geometry or type;
- an invalid layer grouping;
- no valid host output for hosted elements;
- walls that no longer match the required source condition; and
- a view that does not support the workflow.

Warnings may also identify conditions that require review but do not prevent the operation.

---

## Run the Separation

Choose **Separate walls** after reviewing every wall type.

For each supported source wall, Wall Manager:

- records the original wall and separation configuration;
- creates the configured output walls at the original wall location;
- preserves supported wall constraints and orientation;
- heals compatible joins where possible;
- rehosts supported doors and windows;
- removes the original compound wall; and
- records the generated set for later recreation.

The operation is applied to Revit as one undoable action.

---

## Check the Result

After separation, review:

- wall alignment in plan and 3D;
- exterior-to-interior layer order;
- wall joins at ends and intersections;
- door and window cuts;
- hosted-element parameter values; and
- the intended host wall.

If the host was chosen incorrectly, use Wall Manager's host-change workflow rather than manually rebuilding the opening.
