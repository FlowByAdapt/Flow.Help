# Creating Area Envelopes

Use **Area Envelope** to create a closed set of Revit Area Boundary Lines from selected exterior perimeter walls. You can then place an Area and leaderless Area Tag inside the new boundary, or keep the boundary lines only.

---

## Before You Begin

The project must already contain a suitable Area Plan for the workflow you want to use.

The standard Area Scheme names are:

* **Area to Cladding** for **Cladding Area**.
* **Area to Framing** for **Framing Area**.

Flow also recognises scheme names that clearly identify the same purpose, including common variants such as **A2C** and **A2F**. It does not create the Area Scheme or Area Plan.

The selected perimeter must consist of:

* at least three walls;
* straight **Basic Walls**;
* one continuous, unbranched closed perimeter.

Curved walls and non-Basic wall types are not currently supported.

---

## 1. Choose Cladding or Framing

On the Revit ribbon:

**Flow → Model → Areas**

Choose:

* **Cladding Area** — creates the boundary at the exterior wall face.
* **Framing Area** — creates the boundary at the exterior boundary of the wall core.

You can also start either workflow directly from Flow Hub.

See [Framing and Cladding](framing-and-cladding.md) for more detail about the two boundary positions.

---

## 2. Select the Perimeter Walls

You can either preselect the walls before starting Area Envelope or select them after the tool starts.

When Revit enters wall-selection mode:

1. Select all walls that form the required exterior perimeter.
2. Use Revit's native **+ / −** selection controls to add or remove walls.
3. Click **Finish** when the complete perimeter is selected.

Only wall elements can be selected. Duplicate wall selections are ignored.

The order in which you select the walls does not matter. Flow determines their connected order from the wall geometry.

!!! tip "Preselect complex perimeters"

    If the perimeter contains many walls, preselect them before launching Area Envelope. The preselected walls are loaded into Revit's native selection session so you can review, add to, or remove from the selection before clicking **Finish**.

!!! warning "Complete the perimeter"

    Select one continuous closed loop. Missing walls, disconnected wall groups, branches or T-junctions cannot form a valid Area Envelope.

<!-- SCREENSHOT: Revit native wall-selection mode with the complete perimeter highlighted and the + / − selection cursor visible, before clicking Finish. -->

---

## 3. Flow Activates the Area Plan

Area Envelope creates the result in an existing Area Plan using a matching Area Scheme.

If the active view is already a suitable Area Plan, Flow keeps it active. Otherwise it looks for a matching Area Plan in this order:

1. a matching Area Plan on the same level as the current plan view;
2. an already open matching Area Plan;
3. a matching Area Plan whose name identifies the ground floor;
4. the lowest-level matching Area Plan.

Flow may therefore switch views as part of the workflow.

!!! note "Flow does not create Area Plans"

    If no suitable Area Plan exists, create the required Area Scheme and Area Plan in Revit, then run Area Envelope again.

---

## 4. Flow Creates the Boundary

After selection is finished, Flow validates the walls and builds the perimeter automatically.

Flow:

* checks that the walls provide supported straight Basic Wall geometry;
* connects the wall location lines into one closed loop;
* tolerates and resolves small wall-end discrepancies of approximately 10 mm;
* derives the required cladding or framing/core boundary position;
* trims adjoining boundary lines to their intersections;
* checks the final boundary for gaps, overlaps, crossings and invalid geometry;
* creates the Area Boundary Lines together in the activated Area Plan.

The selected perimeter walls remain selected in Revit after you click **Finish**, making it easier to see which walls were used.

If the boundary cannot be created, the boundary transaction is rolled back and no partial set of Area Boundary Lines is retained.

---

## 5. Choose How to Place the Area

Once the Area Boundary Lines have been successfully created, the **Place Area** window appears.

Choose one of the following options.

### Auto Area + Tag

Flow calculates the polygon centroid of the generated boundary and attempts to create:

* one Area;
* one leaderless Area Tag.

For simple regular envelopes this normally provides a suitable placement point. The centroid of a highly irregular or concave boundary is not guaranteed to fall inside the enclosed region, so automatic placement can fail even when the boundary itself is valid.

### Manual Area + Tag

Pick a point inside the new closed boundary. Flow creates the Area and a leaderless Area Tag at that point.

Use this option when the automatic placement point is unsuitable or when you want direct control over the Area location.

### Boundary Only

Keep the Area Boundary Lines without creating an Area or Area Tag.

Closing the **Place Area** window without choosing an option also leaves the result as **Boundary Only**.

<!-- SCREENSHOT: Place Area window showing Auto Area + Tag, Manual Area + Tag and Boundary Only. -->

!!! info "Boundary lines are created first"

    Boundary creation and Area placement are separate operations. If manual point selection is cancelled, or the Area and tag cannot be created, the successfully created Area Boundary Lines remain in the model.

---

## Expected Result

In the activated Area Plan, a successful run produces:

* one closed set of Area Boundary Lines following the selected cladding or framing/core position;
* an Area, if **Auto Area + Tag** or **Manual Area + Tag** succeeds;
* a leaderless Area Tag, placed with that Area;
* the original perimeter walls still selected in Revit after the wall-selection stage.

<!-- SCREENSHOT: Completed Area Plan result showing Area Boundary Lines, Area and leaderless Area Tag. -->

---

## Automatic Behaviour to Be Aware Of

Area Envelope automatically handles several parts of the workflow:

* wall selection order is resolved from geometry;
* duplicate wall selections are ignored;
* small endpoint discrepancies are treated as connected within the tool's tolerance;
* an appropriate existing Area Plan can be activated automatically;
* corners are trimmed from the derived boundary lines;
* the Area and Area Tag are created together in a separate placement transaction;
* the Area Tag is created without a leader;
* successfully committed boundary lines are retained if later Area placement is cancelled or fails.

Area Envelope does **not** automatically remove an earlier result. Running the tool repeatedly in the same location can create overlapping Area Boundary Lines.

---

## Current Limitations

Area Envelope currently requires:

* straight **Basic Walls**;
* one continuous closed perimeter;
* no branches or T-junctions in the selected loop;
* usable planar exterior wall-face geometry;
* an existing matching Area Plan and Area Scheme.

For **Framing Area**, the result depends on the wall's compound structure and core definition. See [Framing and Cladding](framing-and-cladding.md).

For selection, geometry or placement problems, see [Troubleshooting](troubleshooting.md).

---

## Related Help

* [Area Envelope](index.md)
* [Framing and Cladding](framing-and-cladding.md)
* [Troubleshooting](troubleshooting.md)
