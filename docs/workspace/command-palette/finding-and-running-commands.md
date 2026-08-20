# Finding and Running Commands

The **Command Palette** provides a fast search-based interface for finding Flow tools and native Revit commands.

When a search is active, indexed library content can also be included in the results.

---

## Search

Open Command Palette and start typing in the **Search** box.

You do not need to enter the complete command name.

Flow can match search text against information including:

- command names;
- aliases;
- keywords;
- descriptions; and
- categories.

This allows you to search using the part of a command or workflow that you remember.

!!! tip "Start with the recognisable part"

    If you do not know the exact command name, enter the word or phrase you associate with it.

    Continue typing if you need to narrow the results.

---

## Find a Flow Tool

Registered Flow tools are included in Command Palette search.

1. Enter part of the tool or command name.
2. Review the matching results.
3. Select the required Flow command.
4. Run the command.

The selected tool launches using the same Flow functionality available elsewhere in the Flow interface.

---

## Find a Native Revit Command

Command Palette also includes most native Revit commands that Revit makes available for programmatic launching.

Search for the Revit command in the same way as a Flow tool.

Potentially destructive or inappropriate commands, including **Delete**, **Exit Revit**, clipboard operations and project save commands, are deliberately excluded.

!!! info "Revit command availability"

    Command Palette does not reproduce the entire Revit ribbon.

    It exposes most commands that Revit makes available for programmatic launching, with selected commands deliberately excluded.

---

## Find Library Content

When a search is active, Flow can also search the indexed content library for the current Revit version.

Matching content can include Revit families and drafting/detail content.

Content results are presented separately from command results.

For more information about the available content actions, see [**Finding and Loading Content in Flow Hub**](../flow-hub/finding-and-loading-content.md).

---

## How Results Are Ranked

Command Palette considers both the quality of the search match and how commands have previously been used.

Exact and close matches against command names, aliases and keywords are prioritised.

Descriptions and categories can also contribute to a match.

Frequently or recently used commands can receive additional priority.

!!! info "Results can adapt to your usage"

    The order of matching commands can change over time as Flow takes command usage and recency into account.

---

## Filter Commands

Command Palette provides additional filters for narrowing the command list.

### Recent

Use **Recent** to focus the results on recently used commands.

Select it again to return to the normal results.

### Flow

Use the **Flow** filter when you want to focus on Flow commands rather than the wider command set.

Filters can be used together with the Search box to narrow the results further.

!!! tip "Check your filters"

    If a command you expect to see is missing, check whether **Recent** or another filter is currently active.

---

## Run a Command

There are several ways to launch the selected command.

### Run Selected

Select the required command and click **Run Selected**.

### Double-click

Double-click a command in the results to run it immediately.

### Keyboard

Select the required command and press **Enter**.

---

## Navigate with the Keyboard

| Key | Action |
|---|---|
| **↓** | Move to the next result |
| **↑** | Move to the previous result |
| **Enter** | Run the selected result |
| **Esc** | Clear the current search |

!!! tip "Quick keyboard workflow"

    Open **Command Palette**, start typing, use **↑** or **↓** to select the required result, then press **Enter**.

---

## Clear a Search

Press **Esc** to clear the current search.

You can then enter another search without closing Command Palette.

---

## Pin a Useful Command

Commands you use regularly can be pinned for quicker access through Flow's command interfaces.

See [**Pinned and Recent Commands**](pinned-and-recent.md).

---

## Can't Find What You Need?

Try:

1. Shortening the current search.
2. Searching with another recognisable word.
3. Clearing any active filters.
4. Checking whether the command is a Flow or native Revit command.
5. For content, checking whether the item is available in Content Browser.

See [**Troubleshooting**](troubleshooting.md) if the result still cannot be found.

---

## Related Help

- [**Command Palette**](index.md)
- [**Pinned and Recent Commands**](pinned-and-recent.md)
- [**Troubleshooting**](troubleshooting.md)
- [**Flow Hub**](../flow-hub/index.md)
- [**Finding and Loading Content**](../flow-hub/finding-and-loading-content.md)