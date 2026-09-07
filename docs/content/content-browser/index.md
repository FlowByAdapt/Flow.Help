# Content Browser

The **Content Browser** provides a central location for finding, reviewing and loading approved Revit content.

Use it to search the library for the current Revit version, check family status in the active project, load families and drafting views, and open supporting content-management tools.

---

## Open Content Browser

On the Revit ribbon:

**Flow → Content → Browser**

An active Revit document is required. If Content Browser is already open, Flow activates the existing window instead of opening another.

<!-- SCREENSHOT: Content Browser overview.
Show the complete window with search, filters, content list, preview, diagnostics, status strip and action buttons visible. -->

---

## What Do You Want to Do?

### Find Content

Search the indexed library, browse by category, show favourites or recent content, and filter families by their status in the active project.

➡️ [**Browsing and Searching**](browsing-and-searching.md)

### Load Content

Load a family or drafting view, choose required types from a type catalogue, or assemble a queue of content to load together.

➡️ [**Loading Content**](loading-content.md)

### Work with Existing Project Content

Identify loaded and used families, reload one family, or reload selected categories of project families from the current library.

➡️ [**Project Content**](project-content.md)

### Use Item Actions

Right-click content to open source files and folders, manage previews and type catalogues, extract drafting views, copy a resolved path or reload a family.

➡️ [**Content Actions**](content-actions.md)

### Use Additional Tools

Open the **Tools** menu for sheet, view, project, family-file and library-maintenance utilities.

➡️ [**Content Browser Tools**](content-browser-tools.md)

### Resolve a Problem

Use the troubleshooting checks when content cannot be found, previewed, loaded or reloaded as expected.

➡️ [**Troubleshooting**](troubleshooting.md)

---

## Content Browser at a Glance

A typical workflow is:

1. Open **Content Browser**.
2. Search or filter the available content.
3. Select an item and review its preview, information and project status.
4. Load it directly, add it to the load queue or use an available right-click action.
5. Review the status strip for the result.

The library and local cache are specific to the Revit version currently running.

!!! tip "Combine the filters"

    Search, category, project status, favourites and recent content can be combined to narrow the results.

---

## Main Areas

- **Search and filters** — narrow the indexed content.
- **Content list** — select one or more families, drafting views, templates or container files.
- **Preview** — display the selected item's PNG preview when available.
- **Content information** — review the file, category, status, resolved paths and type-catalogue diagnostics.
- **Status strip** — review validation, progress and completion messages.
- **Action buttons** — load content, manage the queue, save favourites, rebuild the index or clear the cache.
- **Tools** — open supporting Content Browser utilities.

---

## Library Index and Cache

If the library index is missing, Flow builds it when Content Browser opens. Use **Rebuild Index** after content has been added, removed, renamed or reclassified.

Selecting an item can create a local cached copy of the family, matching type catalogue and preview. Existing cached files are not replaced automatically. Use **Clear Cache** when cached content appears older than the library source.

!!! info "Not every Revit file is indexed"

    Content must use a supported file type and pass the current Flow classification rules. Archive, backup, nested and other deliberately excluded content does not appear in the Browser.

---

## Getting Help

Hover over **Browser** on the Flow ribbon and press **F1** to return directly to this page.

---

## Related Help

- [**Browsing and Searching**](browsing-and-searching.md)
- [**Loading Content**](loading-content.md)
- [**Project Content**](project-content.md)
- [**Content Actions**](content-actions.md)
- [**Content Browser Tools**](content-browser-tools.md)
- [**Troubleshooting**](troubleshooting.md)
