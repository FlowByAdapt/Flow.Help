# Finding and Running Tools

Flow Hub provides a single search interface for finding both **Flow tools** and **native Revit commands**.

Search results update as you type and are ranked to help commonly used and relevant commands appear first.

---

## Search for a Tool or Command

Click in the **Search** box at the top of Flow Hub and start typing what you are looking for.

You do not need to enter the complete command name.

For example, you can search using:

- a command name;
- part of a command name;
- a recognised alias;
- a keyword;
- a command description; or
- a command category.

Flow searches the available registered actions and displays matching results.

!!! tip "Search by what you remember"

    You do not need to know the exact Flow or Revit command name.

    Start with the most recognisable word and refine the search if required.

---

## Flow Tools

Registered Flow tools are included in Hub search.

Search for the tool or workflow you need and select the appropriate result.

Running the result launches the same Flow functionality that is available elsewhere in the Flow interface.

---

## Native Revit Commands

Flow Hub can also find and launch native Revit commands.

Most commands that Revit makes available for programmatic launching are included in the Hub.

Potentially destructive or inappropriate commands, such as **Delete**, **Exit Revit**, clipboard operations and project save commands, are deliberately excluded.

!!! info "Revit command availability"

    Native Revit commands shown in Flow Hub are commands that Revit exposes for programmatic launching.

    The exact commands available can therefore depend on Revit and the current Revit context.

---

## Search Results

When a search is active, Flow Hub separates command results from library content results.

Command results can include different types of Flow actions, including Flow tools and native Revit commands.

Content results are shown separately.

See [**Finding and Loading Content**](finding-and-loading-content.md) for information about library content.

---

## How Results Are Ranked

Flow Hub considers more than a simple text match when ordering command results.

Matches against command names, aliases and keywords are prioritised, while descriptions and categories can also contribute to a match.

Commands you use frequently or have used recently can also receive higher priority.

This means the ordering of results may adapt to the way you use Flow.

!!! info "Results may change over time"

    Frequently and recently used commands can be ranked more highly.

    As a result, two matching commands may not always appear in the same order as your usage changes.

---

## Run a Command

There are several ways to run a selected command.

### Run Selected

Select the required result and click:

**Run Selected**

### Double-click

Double-click a command result to run it immediately.

### Keyboard

Select the required command and press:

**Enter**

The selected Flow or Revit command is then launched.

---

## Navigate with the Keyboard

Flow Hub supports keyboard navigation for quickly searching and launching commands.

| Key | Action |
|---|---|
| **↓** | Move to the next result |
| **↑** | Move to the previous result |
| **Enter** | Run the selected result |
| **Esc** | Clear the current search |

If the search is already clear, **Esc** returns focus to the Search box.

!!! tip "Quick keyboard workflow"

    Enter a search, use **↑** or **↓** to select the required result, then press **Enter** to run it.

---

## Clear the Search

Press:

**Esc**

to clear an active search.

Clearing the search returns Flow Hub to its normal view containing **Quick Actions**, **Pinned**, **Recent** and **Browse**.

---

## Can't Find a Command?

Try:

1. Shortening the current search.
2. Searching using another recognisable word.
3. Clearing the search and trying again.
4. Checking whether the command is available from the Flow or Revit interface.

See [**Troubleshooting**](troubleshooting.md) if the command still cannot be found.

---

## Related Help

- [**Flow Hub**](index.md)
- [**Finding and Loading Content**](finding-and-loading-content.md)
- [**Pinned and Recent Items**](pinned-and-recent.md)
- [**Command Palette**](../command-palette/index.md)