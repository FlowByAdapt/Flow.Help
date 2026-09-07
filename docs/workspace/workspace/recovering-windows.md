# Recovering Windows

Use Workspace recovery when a Revit or Flow window has opened outside the visible desktop.

This commonly happens after changing monitor arrangements or disconnecting a display that was previously being used.

Recovery does **not** require a saved workspace.

---

## When to Use Recovery

Use recovery when:

- a window is open but cannot be seen;
- a window opens on a monitor that is no longer connected;
- the monitor arrangement has changed;
- a floating Revit or Flow window is outside the current desktop; or
- you need to bring one or more off-screen windows back into view.

Recovery is different from **Restore Workspace**.

A workspace restore tries to recreate a saved arrangement.

Recovery simply brings inaccessible windows back onto the current visible desktop.

---

## Recover a Selected Window

Use selected-window recovery when you know which window is missing.

1. Open **Flow → Workspace → Workspace**.
2. Select the required window in the Workspace window list.
3. Select **Recover**.
4. Flow checks whether the window can be moved.
5. If it is off-screen, Flow brings it back onto the visible desktop.

<!-- SCREENSHOT: Workspace individual-window recovery.
Show a window selected in the Workspace window list with Recover and Recover All visible. -->

If the selected window is already visible, Flow reports that it is already on-screen rather than moving it unnecessarily.

---

## Recover All Windows

Use **Recover All** when you are not sure which window is missing or several windows may be off-screen.

1. Open **Flow → Workspace → Workspace**.
2. Select **Recover All**.
3. Flow inspects the current supported windows.
4. Off-screen windows are moved back onto the visible desktop.

If no off-screen windows are found, Flow reports:

**No off-screen windows were found.**

---

## Recover from Flow Hub

Flow Hub also provides:

**Workspace → Recover**

The Hub recovery action uses the shared all-window recovery workflow.

Use the full Workspace window when you want to inspect the available windows or recover a specific selected window.

See [**Flow Hub Workspace Controls**](../flow-hub/workspace-controls.md).

---

## Recovery Does Not Restore a Layout

Recovery does not:

- select a saved workspace;
- require matching monitor topology;
- reopen a complete saved arrangement; or
- return every window to previously saved coordinates.

Its purpose is simply to make off-screen windows accessible again.

If you want to recreate a known saved arrangement, use [**Restoring a Workspace**](restoring-a-workspace.md).

---

## A Selected Window Cannot Be Recovered

If Flow cannot move the selected window:

1. refresh or reopen the Workspace window;
2. confirm that the window still exists;
3. try **Recover All**;
4. complete any modal Revit dialog that may currently be active; and
5. restart Revit if the native window is no longer responding correctly.

---

## After Changing Monitor Arrangements

If you have intentionally changed your normal monitor setup:

1. use **Recover All** to bring inaccessible windows onto the current desktop;
2. arrange the windows for the new setup; and
3. save a new workspace for that monitor arrangement.

This provides a clean layout to restore the next time you use the same setup.

---

## Related Help

- [**Workspace**](index.md)
- [**Saving a Workspace**](saving-a-workspace.md)
- [**Restoring a Workspace**](restoring-a-workspace.md)
- [**Managing Saved Workspaces**](managing-saved-workspaces.md)
- [**Flow Hub**](../flow-hub/index.md)
