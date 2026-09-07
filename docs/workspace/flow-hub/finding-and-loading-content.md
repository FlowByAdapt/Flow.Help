# Finding and Loading Content

Flow Hub can search the indexed Revit content library alongside Flow and Revit commands.

This provides quick access to library content without first opening the full Content Browser.

---

## Search for Content

Library content is added to Flow Hub results only while a search is active.

1. Click in the **Search** box.
2. Enter a recognisable content term.
3. Review the **Content** section of the results.
4. Select the required content item.
5. Run the result to choose what you want to do with it.

Content can be matched using indexed information including:

- content name;
- family name;
- category;
- browser category;
- content type; and
- family or content classification.

!!! tip "Use familiar content terms"

    Search using the name or category you would normally use when looking for the content.

    Flow also supports some common terminology when matching against library naming conventions.

---

## Content You Can Find

Depending on the indexed content library for the current Revit version, results can include:

### Families

Revit family files can appear directly in Hub search.

### Catalogue Families

Families that use a type catalogue can appear as catalogue content.

When they are loaded, Flow can request the required type selection before completing the load.

### Drafting and Detail Content

Indexed drafting/detail content can also appear in Hub search.

---

## Review a Content Result

Depending on the available index information, a content result can include:

- content name;
- category;
- source filename;
- content type;
- result badge; and
- preview image.

Use this information to confirm that you have found the correct item before continuing.

<!-- SCREENSHOT: Flow Hub content search result.
Show the Content section with a result that clearly includes its badge and identifying information. -->

---

## Open a Content Result

Run a content result to choose what you want to do with it.

Available actions can include:

### Open in Content Browser

Opens the item in the full **Content Browser** workflow.

Use this when you want to review the item in more detail before loading or managing it.

### Load into Project

Loads supported content into the active Revit project.

This option is available for supported loadable content such as Revit family content and drafting-view content.

Where further choices are required, Flow displays the appropriate selection interface before loading.

### Reveal in Explorer

Opens the folder containing the selected source content.

### Open Source File

Opens the underlying source file.

### Cancel

Closes the action chooser without proceeding.

<!-- SCREENSHOT: Content action chooser.
Show Open in Content Browser, Load into Project, Reveal in Explorer, Open Source File and Cancel where available. -->

!!! info "Available actions depend on the content"

    Not every action is appropriate for every content type.

    For example, **Load into Project** is only offered when Flow supports directly loading that content into the active project.

---

## Content Favourites

Library content favourites are maintained through **Content Browser** state.

Favourite content can receive higher priority when matching Hub search results are ranked.

This helps preferred library items remain easier to find across Flow's content interfaces.

---

## Recent Content

Recently used content can also receive higher priority in content search results.

This is separate from the Hub's normal **Recent** command section.

---

## Content Is Version-Specific

Flow searches the indexed content library associated with the current Revit version.

If expected content does not appear, confirm that:

1. a search is active;
2. the correct content library is available;
3. the content has been indexed for the Revit version you are using; and
4. the item can still be found in Content Browser.

If the current-version content index is unavailable, Flow Hub cannot return indexed content results.

---

## Content Browser

Flow Hub is intended to provide quick access to content.

Use the full **Content Browser** when you need broader browsing, filtering, family management or larger content workflows.

---

## Related Help

- [**Flow Hub**](index.md)
- [**Finding and Running Tools**](finding-and-running-tools.md)
- [**Pinned and Recent Items**](pinned-and-recent.md)
- [**Troubleshooting**](troubleshooting.md)
