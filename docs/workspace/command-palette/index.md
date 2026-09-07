# Command Palette

The **Command Palette** provides a fast way to find and launch Flow tools, native Revit commands and searchable library content from a floating window.

You can browse commonly used commands immediately or start typing to search across the wider Flow command system.

---

## Open Command Palette

On the Revit ribbon:

**Flow → Workspace → Command**

Command Palette opens as a floating window with the **Search** box ready for input.

If Command Palette is already open, selecting **Command** again returns you to the existing window rather than opening another copy.

<!-- SCREENSHOT: Command Palette immediately after opening.
Show the complete floating window with Search, Quick Actions, Pinned, Recent and Browse visible. -->

---

## What You See When It Opens

You do not need to search before using Command Palette.

With the Search box empty, commands are organised into sections to make commonly used actions easier to reach.

### Quick Actions

Provides convenient access to selected commonly used actions.

### Pinned

Shows commands you have pinned for regular use.

### Recent

Shows commands you have used recently through Flow's command system.

### Browse

Provides access to the wider available command list.

Flow automatically selects the first available result so that you can immediately navigate or run commands using the keyboard.

---

## First-Time Workflow

A typical Command Palette workflow is:

1. Open **Flow → Workspace → Command**.
2. Start typing a recognisable part of the command or content you want to find.
3. Review the matching results.
4. Use the mouse or **↑ / ↓** keys to select a result.
5. Press **Enter**, double-click the result or select **Run**.
6. Complete any additional choices required by the selected command or content item.

Search results update automatically as you type.

!!! tip "You do not need the exact name"

	Flow searches command names and supporting search information such as aliases, keywords, descriptions and categories.

	Start with the word or phrase you associate with the task and refine the search if required.

---

## What Can Command Palette Find?

Depending on your search and current Revit context, results can include:

* **Flow tools and commands**
* **Native Revit commands**
* **Indexed library content**

Commands and content are presented separately when a search is active.

<!-- SCREENSHOT: Search returning a mixture of Flow, Revit and content results.
Choose a search term that clearly demonstrates the different result types. -->

---

## Running Commands

For a Flow or Revit command:

1. Select the required result.
2. Press **Enter**, double-click it or select **Run**.

Flow commands launch through their normal Flow workflow.

Native Revit commands are passed back to Revit and can only run when Revit makes that command available in the current context.

See [**Finding and Running Commands**](finding-and-running-commands.md) for the complete search and execution workflow.

---

## Working with Library Content

Library content becomes available in Command Palette results when a search is active.

Running a content result provides additional choices rather than immediately loading the item.

Depending on the content, these can include:

* **Open in Content Browser**
* **Load into Project**
* **Reveal in Explorer**
* **Open Source File**
* **Cancel**

The available choices depend on the selected content type.

For larger or more detailed content workflows, use **Content Browser**.

---

## What Flow Does Automatically

While you use Command Palette, Flow automatically:

* updates search results as you type;
* selects an available result for keyboard navigation;
* removes commands that are not available in the current Flow context;
* considers previous command usage when ranking results;
* records commands you run for **Recent** behaviour;
* keeps command pin and recent state synchronised with **Flow Hub**; and
* uses Content Browser favourite and recent information when ranking library content.

This means Command Palette can become quicker to use as your normal command history develops.

---

## Command Palette or Flow Hub?

Both **Command Palette** and **Flow Hub** use Flow's shared command and search infrastructure, but support different ways of working.

!!! tip "Which should I use?"

	Use **Command Palette** when you want a compact floating interface that can be opened when required.

	Use **Flow Hub** when you want search, pinned and recent items, content access and workspace controls to remain available in a docked Revit panel.

See [**Flow Hub**](../flow-hub/index.md).

---

## Getting Help

Hover over **Command** on the Flow ribbon and press **F1** to return directly to this page.

---

## Related Help

* [**Workspace Panel**](../workspace/index.md)
* [**Finding and Running Commands**](finding-and-running-commands.md)
* [**Pinned and Recent Commands**](pinned-and-recent.md)
* [**Troubleshooting**](troubleshooting.md)
* [**Flow Hub**](../flow-hub/index.md)