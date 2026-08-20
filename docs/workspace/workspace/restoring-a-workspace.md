# Restoring a Workspace

Restore a saved workspace when you want to return Revit and Flow to a previously saved working arrangement.

---

## Restore a Workspace

1. Connect the monitors used for the workspace you want to restore.
2. Open **Flow → Workspace → Workspace**.
3. Select the required layout from **Saved Workspaces**.
4. Click **Restore Workspace**.
5. Workspace restores the saved working environment.

---

## What Gets Restored?

Workspace restores supported parts of the Revit and Flow working environment, including:

- Saved window positions
- Supported Flow dockable panes
- Revit **Properties**
- Revit **Project Browser**

Recognised Flow windows that formed part of the saved workspace may also be opened automatically if they are not currently open.

!!! info "Flow windows may reopen"

    If a recognised Flow window was open when the workspace was saved, Flow may
    reopen that window as part of restoring the saved working environment.

    This helps recreate the workspace rather than only repositioning windows
    that are already open.

---

## Monitor Configuration

A saved workspace is associated with the monitor arrangement that was active when it was created.

Before restoring a workspace, Flow checks the current display arrangement against the saved arrangement.

!!! warning "Different monitor setup?"

    If the current monitor arrangement does not match the saved workspace,
    restoration is blocked.

    Connect the appropriate monitors or select a workspace created for your
    current setup.

This prevents windows from being restored to locations that do not exist in the current desktop arrangement.

---

## Missing Window?

If you simply need to bring a lost or off-screen window back onto the visible desktop, you do not need to restore an entire workspace.

!!! tip "Lost a window?"

    Use **Recover Windows** instead of restoring an entire workspace when you
    only need to bring an off-screen window back into view.

    Recover Windows does not require a previously saved workspace.

[Recover Windows →](recovering-windows.md)

---

## Related Help

- [Workspace](index.md)
- [Saving a Workspace](saving-a-workspace.md)
- [Managing Saved Workspaces](managing-saved-workspaces.md)
- [Recovering Windows](recovering-windows.md)