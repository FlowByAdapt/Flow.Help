# Active View Controls

The active-view controls in Visibility Manager provide quick access to working and visibility settings for the Revit view you are currently using.

They are organised under **Working Aids**, **Datum Graphics** and **View Controls**.

Some controls deliberately operate through the active view's assigned view template when one is present.

---

## Open Active View Controls

Open:

**Flow → Content → Visibility**

The active-view controls are:

### Working Aids

- **Reference Planes**
- **Room Layout Mode**

### Datum Graphics

- **Grid Bubbles**

### View Controls

- **Section Box**

!!! info "The active view determines the context"

    Open the Revit view you want to work with before changing an active-view control.

    If you change views while Visibility Manager is open, use **Refresh** when you want to immediately confirm the states for the new view.

---

## Reference Planes

Use **Reference Planes** to show or hide reference planes.

If the active view has an assigned view template, Flow deliberately applies the Reference Plane category visibility setting to that template.

If no view template is assigned, Flow applies the setting directly to the active view.

!!! warning "A view template can affect multiple views"

    When Reference Plane visibility is changed through an assigned view template, the result is not limited to the individual active view.

    Other views using the same template can also be affected by the template-controlled setting.

If the Reference Plane category cannot be controlled in the target view or template, the control is shown as unavailable.

---

## Room Layout Mode

Use **Room Layout Mode** when working with room layouts.

This is a coordinated working mode rather than a simple visibility switch, so it uses **Enable** and **Disable**.

### With an Assigned View Template

When the active view has an assigned view template, Flow operates through that template.

**Enable**:

- shows **Room Separation Lines**; and
- hides **Floors**.

**Disable**:

- hides **Room Separation Lines**; and
- shows **Floors**.

This provides a coordinated room-layout presentation through the template.

### Without an Assigned View Template

If the active view does not have an assigned view template, Room Layout Mode changes **Room Separation Line visibility only**.

Floor visibility is not changed in this case.

!!! info "The displayed mode follows Room Separation Lines"

    Visibility Manager reads the Room Layout Mode state from whether Room Separation Lines are currently visible in the target view or template.

---

## Grid Bubbles

Use **Grid Bubbles** to show or hide grid bubbles in the active view.

The control works on grid elements found in that view.

### Show Grid Bubbles

When grid bubbles are shown, Flow first clears the bubbles from both ends and then applies a consistent presentation:

- **vertical grids** display the **top** bubble;
- **horizontal grids** display the **left** bubble.

For grids that are not horizontal or vertical, Flow uses the endpoint with the higher vertical position.

### Hide Grid Bubbles

When grid bubbles are hidden, Flow hides the bubble at **both ends** of each grid in the active view.

<!-- SCREENSHOT: Revit plan after Show Grid Bubbles.
Show vertical grids labelled at the top and horizontal grids labelled at the left. -->

!!! note "Show also standardises presentation"

    **Show** does not simply restore whichever bubble ends were previously visible.

    It deliberately applies Flow's top/left grid-bubble arrangement.

If no grids are found in the active view, the control is unavailable.

---

## Section Box

Use **Section Box** to show or hide the section box boundary in the active 3D view.

The control changes the visibility of the section box element without removing the section box itself.

### Show a Hidden Section Box

Flow can locate a controllable section box even when its boundary is currently hidden in the active 3D view.

Selecting **Show** can therefore restore a previously hidden section-box boundary.

### Requirements

Section Box requires:

- an active **3D view**; and
- a section box element that can be controlled in that view.

If these conditions are not met, the control is shown as unavailable.

!!! info "The section box is not deleted"

    **Hide** hides the section-box element in the active 3D view.

    It does not remove the section box from the view.

---

## Change an Active View Control

1. Open the Revit view you want to work with.
2. Locate the required control in Visibility Manager.
3. Review its current state and description.
4. Select the switch.
5. Flow applies the change.
6. Visibility Manager refreshes the displayed states.

---

## Project or Active View?

Use **Project Graphics** when you want to change the project-wide Flow graphics settings for:

- **3D Doors**
- **Draft Graphics**
- **NFC Graphics**

Use the active-view controls when the setting relates to the view you are currently working in or its assigned view template.

See [**Project Controls**](project-controls.md).

---

## Related Help

- [**Visibility Manager**](index.md)
- [**Project Controls**](project-controls.md)
- [**Troubleshooting**](troubleshooting.md)
