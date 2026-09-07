# Finding and Running Tools

Flow Hub provides a single search interface for finding **Flow tools** and supported **native Revit commands**.

---

## Find a Tool or Command

1. Click in the **Search** box.
2. Start typing what you are looking for.
3. Review the matching results.
4. Select the required result.
5. Press **Enter**, double-click it or select **Run Selected**.

Search results update automatically as you type.

Flow automatically selects the first available result so keyboard-based workflows can continue without needing to reselect an item.

---

## Search

You do not need to enter the complete command name.

Flow can match search text against information including:

- command name;
- part of a command name;
- alias;
- keyword;
- description; and
- category.

!!! tip "Search by what you remember"

    Start with the most recognisable word associated with the task.

    Continue typing only if you need to narrow the results.

---

## Flow Tools

Registered Flow tools are included in Hub search.

Running a Flow result launches the same underlying Flow workflow available elsewhere in the Flow interface.

Some Flow actions are context-sensitive and may not appear when their required Revit context is unavailable.

---

## Native Revit Commands

Flow Hub can also search most Revit commands that Revit exposes for programmatic launching.

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

!!! info "Revit command availability"

    A Revit command appearing in Flow Hub does not mean it can run in every Revit situation.

    Before Flow posts the command, Revit's current command availability is checked.

    Availability can depend on the active document, view, selection or current Revit state.

---

## Search Results

When a search is active, Flow Hub separates results into:

- **Commands**
- **Content**

Command results can include Flow tools and native Revit commands.

Content results are covered separately in [**Finding and Loading Content**](finding-and-loading-content.md).

<!-- SCREENSHOT: Active Flow Hub search.
Show a useful search term with both Commands and Content headings visible if possible. -->

---

## How Results Are Ranked

Flow Hub considers more than a simple text match.

Command ranking can take into account:

- match strength;
- aliases and keywords;
- descriptions and categories;
- frequency of previous use; and
- recency of previous use.

This means result ordering can adapt as you use Flow.

---

## Run a Command

You can run the selected result in several ways.

### Run Selected

Select the required result and click:

**Run Selected**

### Double-click

Double-click a result.

### Keyboard

Select the required result and press:

**Enter**

After a command is handed to its normal Flow or Revit workflow, Flow records its usage and refreshes shared command state.

---

## Keyboard Navigation

| Key | Action |
|---|---|
| **↓** | Move to the next selectable result |
| **↑** | Move to the previous selectable result |
| **Enter** | Run the selected result |
| **Esc** | Clear the current search |

Section headings are skipped when moving through the results.

If the Search box is already clear, **Esc** returns focus to Search.

!!! tip "Fast keyboard workflow"

    Type a search, use **↑** or **↓** to select the required result, then press **Enter**.

---

## Clear the Search

Press:

**Esc**

to clear an active search.

Flow Hub then returns to its normal no-search view containing:

- **Quick Actions**
- **Pinned**
- **Recent**
- **Browse**

---

## Can't Find a Command?

Try:

1. Shortening the current search.
2. Searching with another recognisable word.
3. Clearing the search and trying again.
4. Checking whether the tool is available from the Flow or Revit interface.
5. Confirming that the required Revit context is available.

See [**Troubleshooting**](troubleshooting.md) if the result still cannot be found or run.

---

## Related Help

- [**Flow Hub**](index.md)
- [**Finding and Loading Content**](finding-and-loading-content.md)
- [**Pinned and Recent Items**](pinned-and-recent.md)
- [**Command Palette**](../command-palette/index.md)
