# Hosted Elements

Wall Manager supports wall-hosted **doors and windows** during separation and recreation.

The selected output host wall remains joined with the other generated layer walls so supported openings can cut the separated assembly correctly.

---

## Choose the Host Before Separation

When the source walls contain doors or windows:

1. Review the proposed output groups.
2. Select the wall that should host the openings.
3. Choose **Set selected as host**.
4. Confirm the host indicator before separating the walls.

The selected wall should represent the construction layer intended to control the opening.

---

## What Wall Manager Preserves

For supported doors and windows, Wall Manager preserves applicable:

- family and type;
- location and orientation;
- sill or level relationship;
- instance parameter values; and
- global parameter associations.

Revit may create a replacement family instance as part of rehosting. Wall Manager coordinates the replacement so the resulting opening retains its supported information.

---

## Frame Setback

**Frame Setback** is intentionally treated differently.

For a rehosted door or window, where the parameter is available and writable, Wall Manager:

1. removes the existing global parameter association from **Frame Setback**; and
2. sets **Frame Setback** to **0.0 mm**.

Other supported global parameter associations are retained.

---

## Change an Incorrect Host

If the generated walls were separated with the wrong host:

1. Select a generated wall from the separation operation.
2. Open Wall Manager.
3. Select the required generated output wall.
4. Choose **Set selected as host**.

Wall Manager updates the recorded host and rehosts supported openings where possible.

Review the opening cuts and parameter associations after the change.

---

## Current Limitations

The current workflow is focused on conventional wall-hosted doors and windows.

Curtain walls, curtain panels and curtain-wall-hosted content are outside the current scope. Other specialist hosted families should be reviewed manually after separation.
