# Wall Manager Troubleshooting

## Wall Manager Will Not Open

Confirm that:

- a Revit project is open;
- the active view is a Floor Plan, Ceiling Plan, Structural Plan or 3D view; and
- at least one supported wall can be selected.

Wall Manager does not run in sheets, schedules, elevations, sections or unsupported view types.

---

## A Selected Wall Is Missing

Wall Manager currently supports compound Basic Walls. Curtain walls and unsupported wall forms are not included.

If Wall Manager is already open, select the additional wall in Revit and choose **Add selected**.

---

## Remove Selected Clears More Than Expected

**Remove selected** uses the current Revit selection. Select only the walls that should leave the working set before choosing the command.

Use **Clear** only when the complete Wall Manager working set should be emptied.

Neither command changes the Revit model.

---

## Layers Cannot Be Combined

Hold **Ctrl** while selecting two or more source layers.

The layers must be adjacent in the original compound structure. Non-adjacent layers cannot form one continuous output wall and are intentionally rejected.

---

## The Wrong Output Wall Hosts Openings

Select a generated wall from the recorded separation operation, open Wall Manager, select the intended host output, and use **Set selected as host**.

Then review the door or window cut and its parameters.

---

## A Door or Window Does Not Cut Correctly

Check that:

- the intended generated wall is recorded as the host;
- the generated walls are still aligned;
- compatible generated walls are joined; and
- the family is a supported conventional wall-hosted door or window.

Curtain-wall-hosted content is not currently supported.

---

## Frame Setback Changed

This is expected. For rehosted doors and windows, Wall Manager removes the global parameter association from **Frame Setback** and sets it to **0.0 mm**.

Other supported global parameter associations should remain associated.

---

## Recreation Is Blocked

Recreation is blocked when Wall Manager cannot safely match the generated wall set to its recorded original condition.

Check whether a generated wall has been deleted or substantially altered. Join changes alone should not normally prevent recreation.

If later modelling changes must be retained, do not force recreation. Review the wall manually or undo the relevant changes where appropriate.

---

## Wall Joins Need Review

Wall Manager attempts to heal nearby compatible walls and prefers corresponding generated layer walls at the ends of separated walls.

Complex intersections can still require Revit's **Edit Wall Joins**, **Allow Join** or **Disallow Join** controls. Review corners and junctions after batch separation or recreation.
