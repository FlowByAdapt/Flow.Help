# Area Envelope Troubleshooting

Use the following checks if Area Envelope cannot create the expected Area Boundary Lines, Area, or Area Tag.

---

## The Required Area Plan Cannot Be Found

Area Envelope requires an existing Area Plan using a matching Area Scheme.

The standard scheme names are:

* **Area to Cladding** for Cladding Area;
* **Area to Framing** for Framing Area.

Flow also recognises names that clearly identify the same purpose, including common **A2C** and **A2F** variants.

If Flow cannot find a suitable plan:

1. Confirm that the required Area Scheme exists.
2. Confirm that at least one Area Plan has been created using that scheme.
3. Run the tool again.

!!! note "Flow does not create Area Plans"

    The tool activates a suitable existing Area Plan but does not create the Area Scheme or Area Plan for you.

---

## The Boundary Is Created in the Wrong Area Plan

If several matching Area Plans exist, Flow selects a plan using a defined preference order.

It first keeps an already active matching Area Plan. Otherwise it prefers:

1. a matching Area Plan on the same level as the current plan view;
2. an already open matching Area Plan;
3. a matching ground-floor Area Plan;
4. the lowest-level matching Area Plan.

If you need a particular plan, activate the required matching Area Plan before running Area Envelope.

---

## Walls Cannot Be Selected

Only Revit wall elements are accepted during wall selection.

Check that:

* you are selecting walls in the active Revit model;
* the required walls are visible and selectable;
* no modal Revit command or transaction is already active.

You may preselect walls before launching Area Envelope or select them when prompted.

---

## A Mis-click Ends or Clears the Selection

Wall selection uses Revit's native multi-selection interface. Use the **+ / −** cursor and click **Finish** only when the complete perimeter is selected.

Revit does not expose a cancelled partial selection to Flow, so Flow cannot recover walls that were selected during an interrupted selection session.

!!! tip "Preselect complex perimeters"

    For a large or difficult perimeter, preselect the walls before launching Area Envelope. The preselected walls are loaded into the native selection session so they can be reviewed, added to, or removed from before clicking **Finish**.

---

## A Wall Is Reported as Unsupported

Area Envelope currently supports straight **Basic Walls** only.

The workflow can fail if the selection contains:

* a non-Basic wall type;
* a curved wall;
* a wall without a usable location curve;
* a wall whose exterior side does not provide usable planar face geometry.

Replace or exclude the unsupported wall and run the tool again.

---

## Area Boundary Lines Are Not Created

Flow requires at least three validated walls that can be resolved into one closed perimeter.

Check for:

* a missing perimeter wall;
* disconnected wall groups;
* a branch or T-junction in the selected walls;
* large gaps between wall ends;
* overlapping or crossing perimeter geometry;
* parallel neighbouring boundary segments that cannot be resolved into a corner;
* zero-length or collapsed boundary segments;
* unsupported wall geometry.

Selection order does not matter. Flow orders the selected walls from their connected geometry.

Small wall-end discrepancies of approximately 10 mm can be treated as connected, but larger gaps can prevent the loop from being formed.

If boundary creation fails, Flow rolls back the boundary transaction and does not retain a partial set of Area Boundary Lines.

---

## The Boundary Is on the Wrong Side of a Wall

Both Cladding and Framing boundaries are derived from the wall's exterior side.

If the result is on the wrong side:

1. Check the wall's exterior/interior orientation in Revit.
2. Confirm that you selected **Cladding Area** or **Framing Area** as required.
3. For Framing Area, check the wall type's compound structure and core boundaries.
4. Correct the wall definition or orientation and run the tool again.

---

## Framing and Cladding Produce the Same Boundary

**Framing Area** is calculated from the exterior boundary of the wall core. Flow offsets inward from the exterior wall face by the total thickness of layers outside the first core layer.

If the wall does not provide a usable core definition, that inset can be zero. The Framing Area boundary may then coincide with the Cladding Area boundary.

Check the wall type's compound structure and core boundary settings in Revit.

---

## The Area or Area Tag Is Not Created

The Area and tag are created together after the boundary has already been committed.

If Area or tag creation fails, the placement transaction is rolled back while the Area Boundary Lines remain.

Check that:

* the boundary forms a valid closed region;
* the placement point lies inside the intended region;
* another Area does not already occupy the region;
* the active Area Plan permits Area and tag creation.

If automatic placement does not work, run the tool again and choose **Manual Area + Tag**, then select a clear point inside the boundary.

---

## Auto Area + Tag Does Not Work on an Irregular Boundary

Automatic placement uses the polygon centroid of the generated boundary.

For a concave or highly irregular shape, the centroid is not guaranteed to lie inside the enclosed region. The boundary can therefore be valid even though automatic Area placement fails.

Run the tool again and choose **Manual Area + Tag**, then pick a point clearly inside the required region.

---

## Manual Area Placement Was Cancelled

Cancelling the manual point selection does not remove the Area Boundary Lines. The result is retained as a boundary-only output.

To add the Area afterwards, use Revit's standard Area and Area Tag tools, or rerun Area Envelope after removing the earlier boundary lines if a complete replacement is required.

---

## I Closed the Place Area Window

Closing the **Place Area** window without choosing **Auto Area + Tag**, **Manual Area + Tag**, or **Boundary Only** is treated as **Boundary Only**.

The Area Boundary Lines remain, but no Area or Area Tag is created.

---

## Duplicate Boundary Lines Are Created

Area Envelope does not replace or remove an earlier result automatically. Running it more than once in the same location can create overlapping Area Boundary Lines.

Delete the unwanted earlier boundary lines before running the tool again.

---

## Area Envelope Cannot Run in This File

Area Envelope is intended for Revit project documents. It does not run in Revit family documents.

Open the required project file and run the tool again.

---

## Related Help

* [Area Envelope](index.md)
* [Creating Area Envelopes](creating-area-envelopes.md)
* [Framing and Cladding](framing-and-cladding.md)
