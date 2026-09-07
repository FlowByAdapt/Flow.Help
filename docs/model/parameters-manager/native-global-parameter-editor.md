# Native Global Parameter Editor

Use **Open Native GP Editor** to open Revit's own Global Parameters interface from Parameters Manager.

This is useful for GP operations and value types that the Opening GP Dashboard does not expose directly.

**Ribbon:** Flow → Content → Parameters Manager

---

## When to Use the Native Editor

Use Revit's native editor when you need to:

- Review the complete Global Parameter list
- Inspect GPs excluded from the Opening GP Dashboard
- Edit Integer or Yes/No values
- Work with Element-valued or otherwise unsupported dashboard values
- Review formulas or other native GP settings
- Check a value whose units are not represented appropriately by the Flow dashboard

---

## Open the Native Editor

1. Open the required Revit project.
2. Open **Parameters Manager**.
3. Expand **Maintenance**.
4. Select **Open Native GP Editor**.
5. Continue in Revit's **Global Parameters** interface.

Flow checks whether the current Revit version makes the native Global Parameters command available and whether Revit can post it in the current state.

When available, Flow posts Revit's own command. The editor that opens is a Revit interface rather than a separate Flow window.

<!-- SCREENSHOT: Revit's native Global Parameters window opened from Parameters Manager, with several representative values visible. -->

---

## If the Native Editor Does Not Open

When Revit does not expose the command to Flow, Parameters Manager displays these alternatives:

- Use the Revit shortcut **GG**, or
- Open **Global Parameters** from Revit's **Manage** tab

If Flow encounters an unexpected error while trying to post the command, it displays an error message with the Revit exception detail.

---

## After Making Changes

Changes made in Revit's native editor are not automatically reflected in the existing Flow dashboard scan.

After closing the native editor:

1. Return to **Parameters Manager**.
2. Expand **Audit**.
3. Select **Refresh Dashboard**.
4. Confirm the updated values or association status where applicable.

GPs outside the dashboard's opening-focused scope will remain absent from the Flow grid even after refreshing.

---

## Expected Result

When Revit permits the command, its native Global Parameters interface opens for the active project.

Flow does not create, edit or remove a GP merely by opening the native editor. Any changes result from the actions you perform in Revit's interface.

---

## Current Limitations

- An active Revit project is required.
- Availability depends on whether the current Revit version exposes the command through its postable-command API.
- Revit can prevent a command from being posted in some application states.
- Parameters Manager does not automatically refresh after native-editor changes.
- The complete native interface and its available controls are determined by Revit.

---

## Related Help

- [Parameters Manager](index.md)
- [Editing Global Parameter Values](editing-global-parameter-values.md)
- [Reviewing Global Parameters](reviewing-global-parameters.md)
- [Reviewing Associations](reviewing-associations.md)
- [Parameters Manager Troubleshooting](troubleshooting.md)
