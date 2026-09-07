# Editing Global Parameter Values

Use the **Opening GP Dashboard** to edit supported Global Parameter values directly from Parameters Manager.

**Ribbon:** Flow → Content → Parameters Manager

---

## Before You Start

Open the Revit project containing the Global Parameter you want to change.

Changing a Global Parameter can update every associated element in the project. If you are unsure what the GP controls, use **Review Associations** or Revit's native Global Parameters editor before changing its value.

!!! warning "Project-wide effect"

	A Global Parameter is not an isolated dashboard value. Editing it can change multiple windows, doors or other associated elements throughout the Revit project.

---

## Identify an Editable Value

1. Open **Parameters Manager**.
2. Find the required GP in the dashboard grid.
3. Look for the edit indicator beside its **Current Value**.

The edit indicator identifies values that Parameters Manager allows you to edit directly.

<!-- SCREENSHOT: Dashboard showing one editable Current Value with its edit indicator and one read-only value for comparison. -->

---

## Edit a Value

1. Double-click the editable **Current Value** cell.
2. Enter the new value.
3. Press **Enter**, press **Tab**, or move away from the cell to commit the edit.
4. Select **Audit → Refresh Dashboard**.
5. Confirm that the displayed value matches the intended result.
6. Check representative associated elements in Revit where appropriate.

When the cell edit is committed, Flow sends the change to Revit and applies it inside a transaction.

<!-- SCREENSHOT: Current Value cell in edit mode with a representative value being entered. -->

---

## Values You Can Edit

The current dashboard allows direct editing for:

- **Text** values
- **Length / Number** values represented by a Revit double value

The dashboard currently treats these as read-only:

- **Integer / Yes-No**
- **Element**
- Unsupported or unknown value types
- **Zero Window Sill Height**

Use **Maintenance → Open Native GP Editor** when you need to edit a value that Parameters Manager does not expose.

---

## Entering Lengths and Angles

### Length / Number

Enter non-angle double values as millimetres.

For example:

- Enter `20` for 20 mm
- Enter `2000` for 2000 mm

### Angles

When the GP name contains the word **Angle**, enter the value in degrees.

For example:

- Enter `15` for 15 degrees
- Enter `90` for 90 degrees

!!! note "Name-based interpretation"

	The dashboard identifies an angle from the GP name, not from a separate user-selected unit option. A double GP whose name contains **Angle** is treated as degrees; other double GPs are treated as millimetres.

	Use Revit's native editor if that interpretation is unsuitable for the parameter.

---

## What Happens Automatically

When an edit is committed, Flow:

1. Retrieves the GP from the current Revit project.
2. Interprets the entered text according to the displayed value type.
3. Converts millimetres or degrees to Revit's internal units where required.
4. Sets the new Global Parameter value.
5. Commits the Revit transaction when successful.

Flow does not automatically rescan the dashboard after a successful edit. Use **Refresh Dashboard** to verify the stored value.

---

## Expected Result

After a successful edit and dashboard refresh:

- The GP displays the new value.
- Revit updates supported associated parameters and elements.
- Any resulting model changes are visible in the relevant Revit views.

The extent of the model change depends on how many parameters are associated with that GP.

---

## If the Value Does Not Change

Check the following:

1. Confirm that the cell showed the edit indicator.
2. Use a plain numeric value without unit text for a length or angle.
3. Commit the cell by pressing **Enter**, **Tab**, or moving away from it.
4. Select **Refresh Dashboard**.
5. Confirm that the GP is not controlled by a formula or another Revit restriction.
6. Try the same value in Revit's native Global Parameters editor.

Invalid numeric input is rolled back and may not produce a separate validation message. The typed text can remain visible until the dashboard is refreshed.

If Revit rejects an otherwise valid update, Flow displays an error identifying the GP that could not be changed.

---

## Current Limitations

- Integer and Yes/No values are not editable from the dashboard.
- Element-valued GPs are not editable from the dashboard.
- `Zero Window Sill Height` is deliberately protected from dashboard editing.
- Double-value unit interpretation is based partly on the GP name.
- Invalid numeric input does not currently produce a dedicated input warning.
- The dashboard does not refresh automatically after editing.
- Revit may reject formula-controlled, reporting, read-only or otherwise constrained values.

---

## Related Help

- [Parameters Manager](index.md)
- [Reviewing Global Parameters](reviewing-global-parameters.md)
- [Reviewing Associations](reviewing-associations.md)
- [Native Global Parameter Editor](native-global-parameter-editor.md)
- [Parameters Manager Troubleshooting](troubleshooting.md)
