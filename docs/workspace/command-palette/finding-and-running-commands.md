# Finding and Running Commands

The **Command Palette** provides a fast search-based interface for finding Flow tools, native Revit commands and indexed library content.

---

## Open Command Palette

On the Revit ribbon:

**Flow → Workspace → Command**

The floating Command Palette opens with the **Search** box focused and ready for input.

You can either browse the commands already displayed or start typing to search.

---

## Find and Run a Command

For most commands:

1. Start typing in the **Search** box.
2. Review the matching results.
3. Select the required result.
4. Press **Enter**, double-click the result or select **Run**.
5. Complete the normal Flow or Revit workflow for that command.

Search results update automatically as you type.

Flow automatically selects the first available result, allowing you to search and run many commands without leaving the keyboard.

---

## Search

You do not need to enter the complete command name.

Flow can match search text against information including:

* command names;
* aliases;
* keywords;
* descriptions; and
* categories.

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

The selected tool launches through the same Flow functionality used elsewhere in the Flow interface.

---

## Find a Native Revit Command

Command Palette also includes most native Revit commands that Revit makes available for programmatic launching.

Search for them in the same way as Flow commands.

For safety and suitability, the following Revit commands are deliberately excluded:

* **Exit Revit**
* **Close**
* **Delete**
* **Cut to Clipboard**
* **Copy to Clipboard**
* **Paste from Clipboard**
* **Save**
* **Save As Project**
* **Save As Template**

!!! info "Revit command availability"

	A Revit command appearing in Command Palette does not mean it can run in every Revit situation.

	Before launching a native Revit command, Flow checks whether Revit currently allows that command to be posted.

	Availability can therefore depend on the active document, view, selection or current Revit state.

---

## Find Library Content

Indexed library content is included when text has been entered in the Search box.

Content is searched using information such as its name, category, type and library information.

Matching content is presented separately from command results.

<!-- SCREENSHOT: Search results containing both commands and library content.
Make the separation between command and content results clearly visible. -->

!!! note "Search is required for content"

	Library content is not added to the normal Browse list when the Search box is empty.

	Enter a search term when you want Command Palette to search the content library.

---

## Work with a Content Result

Running a content result opens a choice of available actions rather than immediately loading the item.

Depending on the selected content, you can be offered:

### Open in Content Browser

Opens the item in the full **Content Browser** workflow.

Use this when you want more information or access to the wider Content Browser tools.

### Load into Project

Loads supported content into the active Revit project.

This option is only available for content that supports direct loading through Command Palette.

Additional choices may be required before loading, such as selecting family types.

### Reveal in Explorer

Opens the source location in Windows Explorer.

### Open Source File

Opens the source content file.

### Cancel

Closes the action choices without making a change.

<!-- SCREENSHOT: Content action chooser.
Show Open in Content Browser, Load into Project, Reveal in Explorer, Open Source File and Cancel where available. -->

---

## Load Multiple Content Items

Command Palette can also send a small group of content results through the shared content loading workflow.

1. Search for the required content.
2. Select between **2 and 6** content results.
3. Select **Load Selected**.
4. Review any additional type or loading choices.
5. Confirm the load.

If only one content result is selected, Flow uses the normal single-item content workflow.

!!! warning "Maximum of 6 items"

	**Load Selected** supports a maximum of six content items at a time.

	For larger batches, use **Content Browser**.

<!-- SCREENSHOT: Two or three content results selected with Load Selected visible.
There is no need to demonstrate all six items. -->

---

## How Results Are Ranked

Command Palette considers both the quality of the search match and how commands have previously been used.

Exact and close matches against command names, aliases and keywords are prioritised.

Descriptions and categories can also contribute to a match.

Frequently or recently used commands can receive additional priority.

Content results can also be influenced by favourite and recent content information from Content Browser.

!!! info "Results can adapt to your usage"

	The order of matching results can change over time as Flow builds information about the commands and content you use.

---

## Filter Results

Command Palette provides additional filters for narrowing the command list.

### Recent

Use **Recent** to focus on commands you have recently run through Flow's command system.

Select it again to turn the filter off.

### Flow

Use **Flow** when you only want Flow tools in the command results.

While this filter is active, native Revit commands and other result types are excluded from the filtered command set.

**Flow** and **Recent** can be used together.

!!! tip "Check your filters"

	If a result you expect to see is missing, check whether **Recent** or **Flow** is active.

---

## Keyboard Shortcuts

Command Palette is designed to work efficiently from the keyboard.

| Key            | Action                                              |
| -------------- | --------------------------------------------------- |
| **↓**          | Move to the next selectable result                  |
| **↑**          | Move to the previous selectable result              |
| **Enter**      | Run the selected result                             |
| **Ctrl + 1–9** | Immediately run the corresponding selectable result |
| **Ctrl + F**   | Toggle the selected command's favourite state       |
| **Esc**        | Close Command Palette                               |

Section headings are skipped when moving through the results.

!!! tip "Fast keyboard workflow"

	Open **Command Palette**, start typing, use **↑** or **↓** to select the required command and press **Enter**.

	For results near the top of the list, **Ctrl + 1–9** provides an even faster way to launch them.

!!! note "Esc closes Command Palette"

	**Esc** closes the floating Command Palette.

	It does not clear the Search box while keeping the palette open.

---

## Pin a Useful Command

Commands you use regularly can be pinned for quicker access through Flow's command interfaces.

See [**Pinned and Recent Commands**](pinned-and-recent.md).

---

## Expected Results

After successfully running a Flow or Revit command:

* the requested command is handed to its normal Flow or Revit workflow;
* Flow records the command in its usage history;
* **Recent** information is updated; and
* shared Command Palette and Flow Hub command state is refreshed.

Command Palette normally remains available after running a command unless the selected workflow itself changes the surrounding Revit state.

---

## Limitations

Command Palette is intended as a fast command and content launcher rather than a replacement for the full Flow Hub, Content Browser or Revit ribbon.

In particular:

* library content requires an active search;
* content must be available in the index for the current Revit version;
* only supported content types offer **Load into Project**;
* batch content loading is limited to **2–6 items**;
* native Revit commands depend on Revit's current command availability; and
* selected Revit commands are deliberately excluded from Command Palette.

---

## Can't Find What You Need?

Try:

1. Shortening the current search.
2. Searching with another recognisable word.
3. Turning off active **Flow** or **Recent** filters.
4. Checking whether the command is a Flow or native Revit command.
5. For content, checking whether the item is available in Content Browser.

See [**Troubleshooting**](troubleshooting.md) if the result still cannot be found.

---

## Related Help

* [**Command Palette**](index.md)
* [**Pinned and Recent Commands**](pinned-and-recent.md)
* [**Troubleshooting**](troubleshooting.md)
* [**Flow Hub**](../flow-hub/index.md)
* [**Finding and Loading Content**](../flow-hub/finding-and-loading-content.md)
