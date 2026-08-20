# Creating Area Envelopes

Use **Area Envelope** to create a closed set of Area Boundary Lines from selected exterior perimeter walls. You can then create and tag an Area inside the new boundary.

---

## Before You Begin

The project must already contain an Area Plan using the Area Scheme required by the selected workflow:

* **Area to Cladding** for Cladding Area.
* **Area to Framing** for Framing Area.

Flow finds and opens a matching existing Area Plan. It does not create the Area Scheme or Area Plan.

!!! info "How Flow chooses the Area Plan"

    If the active view is already a matching Area Plan, Flow uses it. Otherwise, Flow looks for a matching Area Plan that is already open, then a ground-floor plan. If no named ground-floor plan is available, it uses the lowest-level matching Area Plan.

---

## Open Area Envelope

On the Revit ribbon:

**Flow → Model → Areas**

Choose:

* **Cladding Area**
* **Framing Area**

The same workflows can be launched directly from Flow Hub.

---

## Select the Perimeter Walls

You can preselect walls before starting the tool or select them when prompted.

1. Select all exterior walls that form the required perimeter.
2. Use Revit's native **+ / −** selection controls to add or remove walls.
3. Click **Finish** when the selection is complete.

Only wall elements can be selected. Duplicate selections are ignored.

!!! warning "Complete the perimeter"

    Select walls that form one continuous closed perimeter. Missing, disconnected, overlapping, or unsuitable wall geometry can prevent Flow from producing a valid boundary.

---

## Choose How to Place the Area

After the Area Boundary Lines have been created, choose one of the following options:

### Auto Area + Tag

Flow calculates a placement point within the generated envelope and creates:

* one Area;
* one leaderless Area Tag.

### Manual Area + Tag

Pick a point inside the new closed boundary. Flow creates the Area and a leaderless Area Tag at that location.

### Boundary Only

Keep the Area Boundary Lines without creating an Area or Area Tag.

!!! info "Boundary lines are retained"

    The boundary is created before Area placement. If manual placement is cancelled, or the Area and tag cannot be created, the successfully created Area Boundary Lines remain in the model.

---

## Review the Result

In the activated Area Plan, confirm that:

* the Area Boundary Lines form the expected closed perimeter;
* the boundary follows the selected cladding or framing position;
* the Area is placed inside the required region, if requested;
* the Area Tag is present and leaderless, if requested.

---

## Related Help

* [Area Envelope](index.md)
* [Framing and Cladding](framing-and-cladding.md)
* [Troubleshooting](troubleshooting.md)