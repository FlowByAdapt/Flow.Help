# Flow Hub Troubleshooting

Use the following checks if Flow Hub, a search result or one of the Hub workspace controls is not behaving as expected.

---

## Flow Hub Is Not Visible

If Flow Hub has been closed, reopen it from the Revit ribbon:

**Flow → Workspace → Hub**

The Hub can then be docked or repositioned as required.

---

## I Can't Find a Flow Tool

First clear the current search and try again.

1. Press **Esc** to clear the search.
2. Enter a shorter or more recognisable search term.
3. Try another word associated with the command.
4. Check whether the tool is available from the **Flow** ribbon.

Flow Hub can search command names, aliases, keywords, descriptions and categories, so you do not always need the exact command name.

---

## I Can't Find a Revit Command

Flow Hub includes most native Revit commands that Revit makes available for programmatic launching.

Some commands are deliberately excluded, including potentially destructive or inappropriate actions such as Delete, Exit Revit, clipboard operations and project save commands.

If a Revit command does not appear, it may not be exposed as an available Revit postable command or may have been deliberately excluded from Flow Hub.

---

## I Can't Find Library Content

Content results are generated from the indexed content library for the current Revit version.

If expected content does not appear:

1. Check that you have entered a search term.
2. Try searching by the family or content name.
3. Try searching by category.
4. Confirm that the appropriate Revit-version content library is available.
5. Check whether the content can be found in the full **Content Browser**.

!!! info "Content appears during search"

    Indexed library content is added to Flow Hub results when a search is active.

    It is not the same as browsing the normal command list with an empty Search box.

---

## Content Will Not Load

If **Load into Project** is available but the content does not load:

1. Confirm that an active Revit project is available.
2. Check that the source content file still exists.
3. Try **Open in Content Browser** and load the content from there.
4. Check any message displayed by Flow during the loading process.

Some content may require additional choices before it can be loaded, such as selecting required family types.

---

## A Content File Cannot Be Found

If Flow reports that the selected content file cannot be found, the indexed library information may no longer match the current content library.

Try locating the item in the **Content Browser**.

If the item is also unavailable there, check the content library or index.

---

## A Command Does Not Run

Make sure an actual command or result is selected.

Try:

- selecting the result and clicking **Run Selected**;
- double-clicking the result; or
- selecting the result and pressing **Enter**.

If a Flow command still does not run, try launching the same tool from the Flow ribbon.

If a native Revit command does not run, it may not be available in the current Revit context.

---

## Search Results Are Not in the Order I Expected

Flow Hub considers both the quality of the text match and your command usage.

Frequently used and recently used commands can receive higher priority.

Favourite and recent library content can also be ranked more highly.

As a result, the ordering of results can change as you use Flow.

---

## My Pinned or Recent Items Look Wrong

Clear the current search first.

The normal Hub view contains the **Pinned** and **Recent** sections.

If the information still appears incorrect, close and reopen Flow Hub and check again.

---

## My Visibility Shortcuts Are Missing

Select:

**Configure**

and check which Visibility Manager controls are selected for Flow Hub.

You can select up to **three** eligible controls.

If three controls are already selected, deselect one before selecting another.

---

## A Visibility Shortcut Does Not Change

The Hub Visibility shortcuts operate through the same visibility controls used by Visibility Manager.

If a shortcut does not change as expected:

1. Wait for any current visibility change to complete.
2. Try the shortcut again.
3. Open the full **Visibility Manager** and check the same control there.

---

## A Saved Workspace Will Not Restore

Check that the required workspace has been selected in the **Layout** list before clicking **Restore**.

If a workspace restoration is already in progress, allow it to finish before requesting another restore.

See [**Restoring a Workspace**](../workspace/restoring-a-workspace.md).

---

## A Window Is Off-Screen

Use:

**Flow Hub → Workspace → Recover**

Flow will attempt to bring Revit and Flow windows back onto the available desktop.

See [**Recovering Windows**](../workspace/recovering-windows.md).

---

## Still Having Problems?

If the problem continues:

1. Check whether the same Flow command works from the Flow ribbon.
2. Check whether content can be found in the Content Browser.
3. Close and reopen Flow Hub.
4. Restart Revit.
5. Confirm that your Flow installation and content library are up to date.

When reporting a problem, include:

- what you were searching for or trying to run;
- your Revit version;
- what you expected to happen; and
- what happened instead.

A screenshot of Flow Hub or any error message can also help identify the problem.

---

## Related Help

- [**Flow Hub**](index.md)
- [**Finding and Running Tools**](finding-and-running-tools.md)
- [**Finding and Loading Content**](finding-and-loading-content.md)
- [**Pinned and Recent Items**](pinned-and-recent.md)
- [**Workspace Controls**](workspace-controls.md)
- [**Visibility Manager**](../visibility-manager/index.md)