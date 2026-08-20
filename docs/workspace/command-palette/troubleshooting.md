# Command Palette Troubleshooting

Use the following checks if you cannot find or launch a result from Command Palette.

---

## Command Palette Is Not Open

Open Command Palette from the Revit ribbon:

**Flow → Workspace → Command**

---

## I Can't Find a Flow Command

First check the current search and filters.

1. Press **Esc** to clear the current search.
2. Turn off **Recent** or other active filters.
3. Enter a shorter or more recognisable search term.
4. Try another word associated with the command.
5. Check whether the command is available from the **Flow** ribbon.

Flow searches command names, aliases, keywords, descriptions and categories, so you do not always need the exact command name.

---

## I Can't Find a Revit Command

Command Palette includes most native Revit commands that Revit makes available for programmatic launching.

Some commands are deliberately excluded, including **Delete**, **Exit Revit**, clipboard operations and project save commands.

If a native Revit command does not appear, it may not be exposed by Revit as an available postable command or may have been deliberately excluded.

---

## I Can't Find Library Content

Indexed library content is added to the results when a search is active.

If expected content does not appear:

1. Make sure you have entered a search term.
2. Try the family or content name.
3. Try searching by category.
4. Confirm that the appropriate content library is available for your Revit version.
5. Check whether the content can be found in the full **Content Browser**.

See [**Finding and Loading Content**](../flow-hub/finding-and-loading-content.md).

---

## Recent Is Hiding Other Commands

If **Recent** is active, Command Palette focuses the results on recently used commands.

Turn **Recent** off and check the results again.

Also check whether another command filter is active.

---

## A Command Does Not Run

Make sure an actual command is selected rather than a section heading.

Then try:

- select the command and click **Run Selected**;
- double-click the command; or
- select the command and press **Enter**.

If a Flow command still does not run, try launching the same tool from the Flow ribbon.

If a native Revit command does not run, it may not be available in the current Revit context.

---

## A Content Result Will Not Load

If the selected result is library content rather than a command, the available actions depend on that content type.

If **Load into Project** fails:

1. Confirm that an active Revit project is available.
2. Check any message displayed by Flow.
3. Try **Open in Content Browser**.
4. Try loading the same content from Content Browser.

Some content may require additional choices, such as selecting required family types.

---

## Search Results Are Not in the Order I Expected

Flow considers both the search match and previous command usage.

Frequently and recently used commands can receive higher priority.

Favourite and recent library content can also be prioritised in content results.

The ordering can therefore change as you use Flow.

---

## My Pinned or Recent Commands Look Wrong

Close and reopen Command Palette and check the command list again.

You can also open **Flow Hub** to compare the pinned and recent command state.

See [**Pinned and Recent Commands**](pinned-and-recent.md).

---

## The Command Works Elsewhere but Not in Command Palette

For a Flow command, try running the same command from the Flow ribbon.

For a Revit command, try running the equivalent command directly in Revit.

If it works there but not from Command Palette:

1. Close and reopen Command Palette.
2. Try the command again.
3. Restart Revit if the problem continues.

---

## Still Having Problems?

If the problem continues, record:

- what you searched for;
- whether the result is a Flow command, Revit command or content item;
- your Revit version;
- your Flow version;
- whether the command works from its normal interface; and
- what happens when you run it from Command Palette.

A screenshot of Command Palette or any error message can also help identify the problem.

---

## Related Help

- [**Command Palette**](index.md)
- [**Finding and Running Commands**](finding-and-running-commands.md)
- [**Pinned and Recent Commands**](pinned-and-recent.md)
- [**Flow Hub**](../flow-hub/index.md)
- [**Flow Hub Troubleshooting**](../flow-hub/troubleshooting.md)