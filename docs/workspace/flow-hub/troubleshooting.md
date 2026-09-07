# Flow Hub Troubleshooting

Use the following checks if Flow Hub, a search result or one of the Hub workspace controls is not behaving as expected.

---

## Flow Hub Is Not Visible

Reopen it from:

**Flow → Workspace → Hub**

The Hub can then be docked or repositioned as required.

If a Flow or Revit window is off-screen, use the Hub **Recover** control.

---

## I Can't Find a Flow Tool

1. Press **Esc** to clear the current search.
2. Enter a shorter or more recognisable search term.
3. Try another word associated with the command.
4. Check whether the tool is available from the Flow ribbon.
5. Confirm that the required Revit context is available.

Flow Hub searches command names, aliases, keywords, descriptions and categories.

Some Flow actions are omitted when they are not available in the current context.

---

## I Can't Find a Revit Command

Flow Hub includes most native Revit commands that Revit exposes for programmatic launching.

The following commands are deliberately excluded:

- **Exit Revit**
- **Close**
- **Delete**
- **Cut to Clipboard**
- **Copy to Clipboard**
- **Paste from Clipboard**
- **Save**
- **Save As Project**
- **Save As Template**

If another Revit command does not appear, it may not be exposed by Revit as a postable command.

---

## A Revit Command Appears but Will Not Run

Native Revit commands depend on the current Revit context.

Before Flow posts the command, Revit's current command availability is checked.

Availability can depend on factors such as:

- whether a project is open;
- the active view;
- the current selection; or
- Revit's current state.

Try the equivalent command directly in Revit to confirm whether it is currently available.

---

## I Can't Find Library Content

Content results are generated from the indexed content library for the current Revit version.

If expected content does not appear:

1. Make sure you have entered a search term.
2. Try the family or content name.
3. Try searching by category or another recognisable term.
4. Confirm that the appropriate Revit-version library is available.
5. Confirm that the content has been indexed for the current Revit version.
6. Check whether the item can be found in the full **Content Browser**.

!!! info "Content appears during search"

    Indexed library content is added to Flow Hub results only while a search is active.

---

## Content Will Not Load

If **Load into Project** is available but the content does not load:

1. Confirm that an active Revit project is available.
2. Complete any family-type or loading choices requested by Flow.
3. Check any Flow message displayed during loading.
4. Confirm that the source content file still exists.
5. Try **Open in Content Browser** and load the content from there.

---

## A Content File Cannot Be Found

If Flow reports that a source file cannot be found, the indexed library information may no longer match the current library.

Try locating the item in **Content Browser**.

If it is also unavailable there, check the content library and rebuild or refresh the relevant content index as appropriate.

---

## A Command Does Not Run

Make sure an actual result is selected rather than a section heading.

Then try:

- clicking **Run Selected**;
- double-clicking the result; or
- pressing **Enter**.

If a Flow command still does not run, try launching the same tool from the Flow ribbon.

---

## Search Results Are Not in the Order I Expected

Flow Hub considers both search match quality and usage history.

Frequently or recently used commands can receive higher priority.

Favourite and recent content information can also affect content ranking.

The ordering can therefore change over time.

---

## My Pinned or Recent Items Look Wrong

First press **Esc** to clear the current search.

The normal Hub view contains **Quick Actions**, **Pinned**, **Recent** and **Browse**.

Command pin and usage state is shared with Command Palette and should normally refresh automatically.

If the display still appears incorrect:

1. check the same command in Command Palette;
2. toggle the pin state again if required; and
3. close and reopen Flow Hub only if the display still appears stale.

Library content favourites and recent content use Content Browser state rather than the normal command pin system.

---

## My Visibility Shortcuts Are Missing

Select:

**Configure**

and check the current shortcut settings.

Only controls configured by Visibility Manager as eligible Hub shortcuts can be selected.

You can select up to **three** controls.

If three are already selected, unselected options are disabled until one of the current three is cleared.

---

## A Visibility Shortcut Does Not Change

The Hub Visibility shortcuts use the same Visibility Manager control infrastructure as the full tool.

When you toggle a shortcut, Flow submits the requested state change and then updates the displayed state from Revit.

If a shortcut does not change as expected:

1. wait for any current visibility request to complete;
2. try the shortcut again;
3. open the full **Visibility Manager**; and
4. check the same control there.

---

## The Wrong Workspace Is Selected

Flow tries to suggest a saved layout that matches the current monitor arrangement.

If several layouts match, the most recently created match is preferred.

If none match, the first available saved layout is selected.

This is only a suggested starting point.

Choose another layout from the **Layout** list before selecting **Restore** if required.

---

## A Saved Workspace Will Not Restore

If the selected workspace cannot be restored, Flow displays a **Workspace Cannot Be Restored** message containing the underlying error.

Check that:

1. the required layout is selected;
2. the Workspace restore external-event service is available; and
3. Revit is in a suitable state for the restore workflow.

See [**Restoring a Workspace**](../workspace/restoring-a-workspace.md).

---

## Workspace Restore Pending

Only one workspace restoration can be pending at a time.

If Flow shows:

**Workspace Restore Pending**

another restore request is already waiting to run.

Allow that request to complete before selecting **Restore** again.

---

## A Window Is Off-Screen

Use:

**Flow Hub → Workspace → Recover**

Flow captures the current native-window state and attempts to bring affected windows back onto the visible desktop.

See [**Recovering Windows**](../workspace/recovering-windows.md).

---

## Esc Behaviour

Flow Hub uses **Esc** differently depending on the current search state.

- If Search contains text, **Esc clears the search**.
- If Search is already clear, **Esc returns focus to the Search box**.

This differs from the floating Command Palette, where **Esc closes the palette**.

---

## Still Having Problems?

If the problem continues:

1. check whether the same Flow command works from the Flow ribbon;
2. check whether content can be found in Content Browser;
3. check equivalent Visibility Manager or Workspace behaviour in the full tool;
4. close and reopen Flow Hub;
5. restart Revit if required; and
6. confirm that Flow and the relevant content library are up to date.

When reporting a problem, include:

- what you were searching for or trying to run;
- whether the issue concerns commands, content, workspace or visibility;
- your Revit version;
- your Flow version;
- what you expected to happen; and
- what happened instead.

A screenshot of Flow Hub and any Flow or Revit message can also help identify the issue.

---

## Related Help

- [**Flow Hub**](index.md)
- [**Finding and Running Tools**](finding-and-running-tools.md)
- [**Finding and Loading Content**](finding-and-loading-content.md)
- [**Pinned and Recent Items**](pinned-and-recent.md)
- [**Workspace Controls**](workspace-controls.md)
- [**Visibility Manager**](../visibility-manager/index.md)
