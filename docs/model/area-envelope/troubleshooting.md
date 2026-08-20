# Area Envelope Troubleshooting

Use the following checks if Area Envelope cannot create the expected Area Boundary Lines, Area, or Area Tag.

---

## The Required Area Plan Cannot Be Found

Area Envelope requires an existing Area Plan using the correct Area Scheme:

* **Area to Cladding** for Cladding Area.
* **Area to Framing** for Framing Area.

If Flow cannot find a suitable plan:

1. Confirm that the required Area Scheme exists.
2. Confirm that at least one Area Plan has been created using that scheme.
3. Run the tool again.

!!! note "Flow does not create Area Plans"

    The tool activates a suitable existing Area Plan but does not create the Area Scheme or Area Plan for you.

---

## Walls Cannot Be Selected

Only Revit wall elements are accepted.

Check that:

* you are selecting walls in the active Revit model;
* the required walls are visible and selectable;
* no modal Revit command or transaction is already active.

You may preselect the walls before launching Area Envelope or select them when prompted.

---

## A Mis-click Ends or Clears the Selection

Wall selection uses Revit's native multi-selection interface. Use the **+ / −** cursor and click **Finish** only when the complete perimeter is selected.

Revit does not expose a cancelled partial selection to Flow, so Flow cannot recover walls that were selected during an interrupted selection session.

!!! tip "Preselect complex perimeters"

    For a large or difficult perimeter, preselect the walls before launching Area Envelope. The preselected walls are loaded into the native selection session so they can be reviewed, added to, or removed from before clicking **Finish**.

---

## Area Boundary Lines Are Not Created

Flow requires at least three validated lines forming a usable perimeter.

Check for:

* a missing perimeter wall;
* gaps or overlaps between wall ends;
* disconnected wall groups;
* unusual wall joins or edited wall profiles;
* wall geometry that does not provide the required cladding or framing position;
* curved or otherwise unsupported perimeter conditions.

Correct the wall geometry or selection, then run the tool again. If boundary creation fails, Flow rolls back the boundary transaction and does not retain a partial set of Area Boundary Lines.

---

## The Boundary Is Created in the Wrong Area Plan

Confirm that the plan uses the correct Area Scheme and level.

If several matching Area Plans exist, open or activate the required matching plan before running Area Envelope. Flow uses an already active matching Area Plan first.

---

## The Boundary Is on the Wrong Side of a Wall

The result depends on the wall's exterior orientation and compound structure.

1. Check the wall's exterior/interior orientation.
2. Confirm that the wall layers and functions are correctly defined.
3. Confirm that you selected **Cladding Area** or **Framing Area** as required.
4. Correct the wall definition or orientation and run the tool again.

---

## The Area or Area Tag Is Not Created

The Area and tag are created together after the boundary has been committed. If either cannot be created, both are rolled back while the Area Boundary Lines are retained.

Check that:

* the boundary forms a closed region;
* the automatic or manually selected point is inside that region;
* another Area does not already occupy the region;
* the active Area Plan permits Area and tag creation.

If automatic placement does not work, run the tool again and choose **Manual Area + Tag**, then select a clear point inside the boundary.

---

## Manual Area Placement Was Cancelled

Cancelling the point selection does not remove the Area Boundary Lines. The result is retained as a boundary-only output.

To add the Area afterwards, use Revit's standard Area and Area Tag tools, or rerun Area Envelope after removing the earlier boundary lines if a complete replacement is required.

---

## Duplicate Boundary Lines Are Created

Area Envelope does not replace or remove an earlier result automatically. Running it more than once in the same location can create overlapping Area Boundary Lines.

Delete the unwanted earlier boundary lines before running the tool again.

---

## Related Help

* [Area Envelope](index.md)
* [Creating Area Envelopes](creating-area-envelopes.md)
* [Framing and Cladding](framing-and-cladding.md)
