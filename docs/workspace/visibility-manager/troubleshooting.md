# Visibility Manager Troubleshooting

Use the following checks if Visibility Manager or one of its controls is not behaving as expected.

---

## Visibility Manager Is Not Open

Open Visibility Manager from the Revit ribbon:

**Flow → Content → Visibility**

Visibility Manager reads all registered control states from the current Revit context when it opens.

---

## The Displayed State Does Not Look Correct

Select **Refresh**.

This reads the current states from Revit again and updates the controls.

Visibility Manager also refreshes automatically after successful Visibility Manager changes and when relevant shared Flow command state changes while the window is visible.

!!! tip "Refresh after changing Revit context"

    Manual Refresh is particularly useful after changing the active Revit view or after changing a related setting directly in Revit.

---

## A Control Is Disabled or Unavailable

An unavailable control normally means that its required Revit context cannot currently be controlled.

Depending on the control, this can include:

- no active Revit document;
- no active Revit view;
- a missing or incompatible global parameter;
- a category that cannot be hidden in the target view;
- no grids in the active view;
- an unsuitable view type; or
- no controllable section box.

Review the control information for the specific warning.

!!! info "Unavailable does not always mean an error"

    A control can be unavailable simply because it does not apply to the current project or view.

---

## A Project Graphics Control Does Not Work

The **3D Doors**, **Draft Graphics** and **NFC Graphics** controls rely on Flow project global parameters.

The required parameters are:

| Control | Required global parameter |
|---|---|
| **3D Doors** | `3D Doors Show` |
| **Draft Graphics** | `Draft Graphics Show` |
| **NFC Graphics** | `NFC Show` |

Check that:

1. an active project is open;
2. global parameters are supported in the document;
3. the required parameter exists; and
4. the parameter contains the expected Yes/No value.

If these requirements are not met, Flow makes the control unavailable and reports the reason.

See [**Project Controls**](project-controls.md).

---

## An Active View Control Affects the Wrong View

Check which Revit view is currently active.

**Reference Planes**, **Room Layout Mode**, **Grid Bubbles** and **Section Box** all begin with the active view as their working context.

However, Reference Planes and Room Layout Mode can deliberately operate through the active view's assigned view template.

Try:

1. Open the required Revit view.
2. Return to Visibility Manager.
3. Select **Refresh**.
4. Check whether the view has an assigned template.
5. Apply the control again.

---

## Reference Planes Behave Differently Than Expected

Check whether the active view has an assigned view template.

If a template is assigned, the **Reference Planes** control targets that template rather than changing only the individual active view.

This means other views using the same template can also reflect the changed Reference Plane visibility.

If no template is assigned, Flow controls Reference Plane visibility directly in the active view.

If the category cannot be controlled in the target view or template, the control is unavailable.

---

## Room Layout Mode Changes Floor Visibility

This can be expected.

When the active view has an assigned view template, **Room Layout Mode** coordinates two categories through that template.

When enabled:

- Room Separation Lines are shown.
- Floors are hidden.

When disabled:

- Room Separation Lines are hidden.
- Floors are shown.

If the active view has **no assigned template**, only Room Separation Line visibility is changed.

If Floor visibility cannot be controlled in the assigned template, Flow cannot apply the coordinated template change.

See [**Active View Controls**](active-view-controls.md).

---

## Grid Bubbles Are Not Where They Were Before

This is expected when using **Show Grid Bubbles**.

Flow does not restore the previous combination of bubble ends.

Instead, it applies a standard arrangement:

- vertical grids → **top bubble**;
- horizontal grids → **left bubble**.

When **Hide** is used, both bubble ends are hidden.

If no grid elements are found in the active view, the control is unavailable.

---

## Grid Bubbles Shows as Visible When Only Some Bubbles Are Visible

Visibility Manager treats Grid Bubbles as **Visible** when at least one grid bubble is currently visible at either end of a grid in the active view.

Selecting the control then applies the complete Show or Hide operation to the grids found in the view.

---

## Section Box Is Unavailable

The **Section Box** control is available only when:

1. the active view is a 3D view; and
2. Flow can find a section box that can be controlled in that view.

If you are in a plan, elevation, section or another non-3D view, the control is unavailable.

---

## My Section Box Exists but Is Hidden

This is supported.

Flow can locate a controllable section box even when its boundary has already been hidden in the active 3D view.

Use **Show** to restore the section-box boundary.

The section box itself is not recreated or replaced.

---

## Colour Tabs Does Not Affect Model Visibility

This is expected.

**Colour Tabs** is an **Application** control.

It colours open Revit document tabs and does not change visibility inside the Revit model or active view.

---

## Change the Colour Tab Appearance

Open **Tab Colour Settings** from Visibility Manager.

Project and Family tabs can use different tab styles.

The default styles are:

- **Project tabs — Background Fill**
- **Family tabs — Top Bar Medium**

Save the settings when you are ready to apply them.

If Colour Tabs is already enabled, Flow reapplies the new settings to the currently open document tabs.

---

## Colour Tab Settings Look Wrong or Have Been Lost

Use **Reset Defaults** in the Tab Colour Settings window to return the selections shown there to Flow's default Project and Family tab styles, then save if you want to retain them.

If Flow cannot load valid saved tab-colour settings, it automatically falls back to its defaults.

---

## A Visibility Change Was Not Accepted by Revit

Visibility Manager applies Revit-dependent changes through Revit's external-event system.

If Revit does not accept a request, Flow displays a **Flow Visibility Manager** message containing the request status.

Allow any current Revit operation to complete and try the control again.

---

## I Am Not Sure Which Control to Use

Use:

- **Project Graphics** for 3D Doors, Draft Graphics and NFC Graphics.
- **Working Aids** for Reference Planes and Room Layout Mode.
- **Datum Graphics** for Grid Bubbles.
- **View Controls** for Section Box.
- **Application** for Colour Tabs.

Hover over an individual control for additional information about what it affects.

---

## Still Having Problems?

If the problem continues, record:

- the visibility control involved;
- your Revit version;
- your Flow version;
- the active Revit view;
- whether the view has an assigned view template, where relevant;
- what you expected to happen; and
- what happened instead.

A screenshot showing both Visibility Manager and the affected Revit view can help identify the problem.

---

## Related Help

- [**Visibility Manager**](index.md)
- [**Project Controls**](project-controls.md)
- [**Active View Controls**](active-view-controls.md)
- [**Flow Hub**](../flow-hub/index.md)
