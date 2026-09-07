# Restoring a Workspace

Restore a saved workspace when you want supported Revit and Flow windows to return to a previously saved arrangement.

---

## Restore a Workspace

Open:

**Flow → Workspace → Workspace**

Then:

1. Select the required saved workspace.
2. Check that it is appropriate for the current monitor arrangement.
3. Select **Restore**.
4. Flow verifies the current monitor topology.
5. The restore request is submitted through Revit.
6. Flow attempts to restore the supported windows and panes in the saved layout.

Workspace restoration can also be requested directly from **Flow Hub**.

---

## Suggested Workspace

When saved layouts are loaded, Flow tries to select a workspace matching the current monitor arrangement.

If several layouts match, Flow prefers the most recently created matching workspace.

If no matching workspace is found, the first available saved layout is selected.

!!! info "The suggested workspace is only a selection"

    Flow does not restore a workspace merely because it has been selected automatically.

    You still choose **Restore**, and the monitor topology is checked again before restoration begins.

---

## Monitor Compatibility

A saved workspace can only be restored when its monitor topology matches the current desktop.

Flow compares:

- the number of monitors;
- monitor positions;
- monitor width and height; and
- the primary-monitor designation.

If the topology does not match, restoration is stopped before the saved window positions are applied.

!!! warning "The same monitor count may still be different"

    Two arrangements can both use two monitors but still be incompatible.

    Moving a monitor from one side to the other, changing its desktop bounds or changing the primary display can make the topology different from the saved workspace.

---

## What Flow Restores

During a compatible restore, Flow works through the saved workspace and attempts to restore supported items.

This includes:

- registered Flow dockable-pane shown/hidden state;
- supported saved window positions and sizes; and
- recognised Flow windows where the required launch support is registered.

Flow also ensures that the Revit **Properties** and **Project Browser** panes are available during the current restore process.

!!! note "Properties and Project Browser"

    The current Workspace restore process ensures these two standard Revit panes are shown when required.

    Do not rely on Workspace to restore a previously saved hidden state for Properties or Project Browser.

---

## Flow Windows That Are Not Open

If a saved window has a recognised Flow identity but is not currently open, Flow can attempt to launch it before restoring its saved position.

After launching, Flow inspects the current windows again and tries to match the newly opened Flow window to the saved one.

Not every Flow window is guaranteed to reopen automatically. Automatic relaunch depends on the window being recognised and having a registered Workspace launcher.

---

## Restore Results

Not every saved window is guaranteed to be restored successfully.

Flow tracks saved windows as:

- **Restored** — the current window was matched and its saved bounds were applied;
- **Unmatched** — Flow could not find a corresponding current window; or
- **Skipped** — a match existed but its saved bounds could not be restored.

A workspace can therefore restore successfully overall while individual windows remain unmatched or skipped.

!!! tip "Use Recover for an off-screen window"

    If the main workspace is usable but a particular window remains outside the visible desktop, use the Workspace recovery tools rather than repeatedly restoring the whole layout.

See [**Recovering Windows**](recovering-windows.md).

---

## Workspace Restore Pending

Only one Workspace restore request can be pending at a time.

If Flow reports:

**Workspace Restore Pending**

another restore request is already waiting to run.

Allow that request to complete before requesting another restore.

---

## Workspace Cannot Be Restored

If Flow reports that the workspace cannot be restored, check:

1. that the required workspace is selected;
2. that the current monitor arrangement matches the saved one;
3. that Revit is in a suitable state for the restore request; and
4. that the relevant Flow windows and panes are available.

If the monitor arrangement has intentionally changed, arrange the current environment as required and either:

- save a new workspace; or
- **Update** the existing workspace.

---

## Restore from Flow Hub

Flow Hub provides a compact Workspace area for restoring saved layouts without opening the full Workspace window.

The Hub uses the same saved workspace library and monitor-matching logic.

See [**Flow Hub Workspace Controls**](../flow-hub/workspace-controls.md).

---

## Related Help

- [**Workspace**](index.md)
- [**Saving a Workspace**](saving-a-workspace.md)
- [**Managing Saved Workspaces**](managing-saved-workspaces.md)
- [**Recovering Windows**](recovering-windows.md)
