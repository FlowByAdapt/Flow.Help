# Project Controls

The project controls in Visibility Manager provide quick access to Flow graphics settings that apply across the current Revit project.

They are grouped under **Project Graphics** and are driven by Flow global parameters in the active project.

---

## Open Project Controls

Open:

**Flow → Content → Visibility**

Locate the **Project Graphics** group.

The group contains:

- **3D Doors**
- **Draft Graphics**
- **NFC Graphics**

---

## Change a Project Control

1. Locate the required control under **Project Graphics**.
2. Review its current state.
3. Select the switch to show or hide the graphics.
4. Flow updates the corresponding project global parameter.
5. Visibility Manager refreshes the displayed states.

!!! tip "The switch reflects the project setting"

    Visibility Manager reads the underlying Revit global parameter rather than maintaining a separate Flow visibility preference.

---

## 3D Doors

Use **3D Doors** to show or hide the project's 3D door graphics.

The control operates the Flow project global parameter:

`3D Doors Show`

Turn the control **on** when 3D door graphics are required.

Turn it **off** when those graphics should be hidden.

---

## Draft Graphics

Use **Draft Graphics** to show or hide drafting graphics across the project.

The control operates the Flow project global parameter:

`Draft Graphics Show`

Turn the control **on** when the project's drafting graphics should be shown.

Turn it **off** when they should be hidden.

---

## NFC Graphics

Use **NFC Graphics** to show or hide NFC graphics across the project.

The control operates the Flow project global parameter:

`NFC Show`

Turn the control **on** when NFC graphics should be shown.

Turn it **off** when they should be hidden.

---

## Requirements

Project Graphics controls require:

- an active Revit document;
- a document that supports Revit global parameters;
- the corresponding Flow global parameter; and
- the global parameter to contain the expected Yes/No value.

If any of these requirements are not met, the corresponding control is shown as unavailable.

The control information provides the reason where possible.

---

## If a Project Control Is Unavailable

Check the corresponding global parameter:

| Control | Required global parameter |
|---|---|
| **3D Doors** | `3D Doors Show` |
| **Draft Graphics** | `Draft Graphics Show` |
| **NFC Graphics** | `NFC Show` |

The parameter must exist in the active project and use the expected Yes/No value.

A control can also be unavailable if there is no active Revit document or if global parameters are not supported by that document.

See [**Troubleshooting**](troubleshooting.md).

---

## Project Controls Are Not View Overrides

These controls operate project-wide Flow graphics settings.

They do not simply apply a visibility override to the active Revit view.

For controls that relate specifically to the current view, use:

- **Working Aids**
- **Datum Graphics**
- **View Controls**

See [**Active View Controls**](active-view-controls.md).

---

## Related Help

- [**Visibility Manager**](index.md)
- [**Active View Controls**](active-view-controls.md)
- [**Troubleshooting**](troubleshooting.md)
