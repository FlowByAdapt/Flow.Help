# Command Palette Troubleshooting

Use the following checks if you cannot find or launch a result from Command Palette.

---

## Command Palette Is Not Open

Open Command Palette from the Revit ribbon:

**Flow → Workspace → Command**

If Command Palette is already open, selecting **Command** again activates the existing window rather than opening another copy.

---

## I Can't Find a Flow Command

First check the current search and filters.

1. Check whether **Recent** or **Flow** is active.
2. Turn off any filter that may be narrowing the results.
3. Shorten the current search term.
4. Try another recognisable word associated with the command.
5. Check whether the command is available from the **Flow** ribbon.

Flow searches command names, aliases, keywords, descriptions and categories, so you do not always need the exact command name.

!!! note "Esc does not clear Search"

    **Esc** closes the floating Command Palette.

    Reopen Command Palette if you close it accidentally.

---

## I Can't Find a Revit Command

Command Palette includes most native Revit commands that Revit exposes for programmatic launching.

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

If another native Revit command does not appear, Revit may not expose it as a postable command.

---

## A Revit Command Appears but Will Not Run

Native Revit commands are dependent on the current Revit context.

Before Flow posts the command, it checks whether Revit currently allows that command to run.

Availability can depend on factors such as:

- whether a project is open;
- the active view;
- the current selection; or
- Revit's current state.

Try the equivalent command directly in Revit to check whether it is currently available.

---

## I Can't Find Library Content

Library content is only added to Command Palette results while a search is active.

If expected content does not appear:

1. Make sure you have entered a search term.
2. Turn off **Flow** or other filters that may be narrowing the results.
3. Try the family or content name.
4. Try searching by category or another recognisable term.
5. Confirm that the appropriate content library has been indexed for your current Revit version.
6. Check whether the content can be found in the full **Content Browser**.

If the current-version content index is unavailable, Command Palette cannot return indexed content results.

See [**Finding and Loading Content**](../flow-hub/finding-and-loading-content.md).

---

## A Content Result Has No Load into Project Option

Not every content type supports direct loading from Command Palette.

**Load into Project** is only offered for supported loadable content.

Other available actions may include:

- **Open in Content Browser**
- **Reveal in Explorer**
- **Open Source File**

Use **Open in Content Browser** when you need the full content workflow.

---

## A Content Result Will Not Load

If **Load into Project** is available but loading does not complete:

1. Confirm that an active Revit project is available.
2. Complete any family type or loading choices requested by Flow.
3. Check any message displayed by Flow.
4. Confirm that the source content file still exists.
5. Try **Open in Content Browser**.
6. Try loading the same content through Content Browser.

If the source file has been moved or removed since the content index was created, Flow may no longer be able to load or open it.

---

## Load Selected Will Not Process My Selection

**Load Selected** is intended for small content batches.

Command Palette supports between **2 and 6 content items** in a batch.

- With **1 item**, Flow uses the normal single-item content workflow.
- With **2–6 items**, Flow can use the batch loading workflow.
- With **more than 6 items**, use **Content Browser** instead.

Additional choices may be required before the batch is loaded.

Cancelling those choices stops the operation.

---

## Recent or Flow Is Hiding Results

Active filters can significantly narrow the result list.

### Recent

Shows commands from your recent Flow command usage.

### Flow

Restricts the filtered command results to Flow tools.

The filters can also be active together.

Turn them off if you want to return to the wider result set.

---

## A Flow Command Does Not Run

Make sure an actual command is selected rather than a section heading.

Then try:

- select the command and click **Run**;
- double-click the command; or
- select the command and press **Enter**.

If the command still does not run, try launching the same tool from its normal location on the Flow ribbon.

Any message displayed by the Flow tool may provide more information about why the workflow cannot start.

---

## Search Results Are Not in the Order I Expected

Flow considers both the quality of the search match and previous usage.

Frequently and recently used commands can receive additional priority.

Favourite and recent library content can also influence content ranking.

The ordering can therefore change as you use Flow.

---

## My Pinned or Recent Commands Look Wrong

Command pin and usage state is shared between Command Palette and **Flow Hub**.

Changes should normally refresh automatically.

If something appears incorrect:

1. Check the same command in Flow Hub.
2. Change the pin state again if required.
3. Close and reopen Command Palette if the display still appears out of date.

Library content favourites and recent content use **Content Browser** state rather than the normal command pin system.

See [**Pinned and Recent Commands**](pinned-and-recent.md).

---

## Keyboard Behaviour Is Not What I Expected

The main Command Palette keyboard controls are:

| Key | Action |
|---|---|
| **↑ / ↓** | Move between selectable results |
| **Enter** | Run the selected result |
| **Ctrl + 1–9** | Run the corresponding selectable result |
| **Ctrl + F** | Toggle the selected command's favourite state |
| **Esc** | Close Command Palette |

In particular, **Esc closes the floating Command Palette** rather than clearing the current search.

---

## The Command Works Elsewhere but Not in Command Palette

For a Flow command, try running the same command from the Flow ribbon.

For a Revit command, try running the equivalent command directly in Revit.

If it works there but not from Command Palette:

1. Check the current Revit context.
2. Close and reopen Command Palette.
3. Try the command again.
4. Restart Revit if the problem continues.

---

## Still Having Problems?

If the problem continues, record:

- what you searched for;
- whether the result is a Flow command, Revit command or content item;
- your Revit version;
- your Flow version;
- whether the command works from its normal interface; and
- what happens when you run it from Command Palette.

A screenshot of Command Palette and any Flow or Revit message displayed when the problem occurs can also help identify the issue.

---

## Related Help

- [**Command Palette**](index.md)
- [**Finding and Running Commands**](finding-and-running-commands.md)
- [**Pinned and Recent Commands**](pinned-and-recent.md)
- [**Flow Hub**](../flow-hub/index.md)
- [**Flow Hub Troubleshooting**](../flow-hub/troubleshooting.md)