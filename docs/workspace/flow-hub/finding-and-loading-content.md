# Finding and Loading Content

Flow Hub can search the indexed Revit content library alongside Flow and Revit commands.

This allows you to find library content without first opening the full Content Browser.

---

## Search for Content

Enter a search in the Flow Hub **Search** box.

When a search is active, Flow searches both available commands and the indexed content library.

Content can be matched using information including:

- content name;
- family name;
- category;
- browser category;
- content type; and
- family or content classification.

Matching library items are displayed separately from command results.

!!! tip "Use familiar content terms"

    Search using the name or category you would normally use when looking for the content.

    Flow also recognises some common search terms against the naming conventions used by the content library.

---

## Content You Can Find

Depending on the contents of the current Revit-version library, search results can include:

### Families

Revit family files can be returned directly in Hub search.

These results are identified as **Family** content.

### Catalogue Families

Families that use a type catalogue are identified as **Catalog** content.

When loaded, Flow uses the normal content-loading workflow so the required types can be selected where necessary.

### Drafting and Detail Content

Indexed drafting/detail content can also appear in Hub search.

These results are identified as **Detail** content.

---

## Review a Content Result

Content results include information to help distinguish them from commands and other content.

Depending on the available library information, this can include:

- content name;
- content category;
- source filename;
- content type;
- result badge; and
- preview image.

Use this information to confirm that you have found the correct library item before continuing.

---

## Open a Content Result

Select or run a content result to choose what you want to do with it.

Available actions can include:

### Open in Content Browser

Opens the **Content Browser** and takes you to the selected content.

Use this when you want to review the item in the full Content Browser before loading it.

### Load into Project

Loads supported content into the active Revit project.

This option is available for loadable content such as Revit families and drafting views.

Where further choices are required, such as selecting types from a catalogue, Flow displays the appropriate selection interface before loading the content.

### Reveal in Explorer

Opens the folder containing the selected source content.

### Open Source File

Opens the underlying source file using its associated application.

!!! info "Available actions depend on the content"

    Not every action is appropriate for every type of library content.

    For example, **Load into Project** is only offered for content that Flow can load into the active project.

---

## Content Favourites

Library content favourites are shared with the **Content Browser**.

Content that has been marked as a favourite can receive higher priority in Hub search results.

This allows frequently used library items to remain easier to find across Flow's content interfaces.

---

## Recent Content

Recently used library content can also receive higher priority in search results.

This helps content you have been working with remain easier to find.

---

## Content Is Version-Specific

Flow searches the indexed content library associated with the current Revit version.

If expected content does not appear, confirm that the appropriate library and content index are available for the Revit version you are using.

See [**Troubleshooting**](troubleshooting.md).

---

## Content Browser

Flow Hub is intended to provide quick access to content.

For broader library browsing, filtering, family management and other content workflows, use the full **Content Browser**.

---

## Related Help

- [**Flow Hub**](index.md)
- [**Finding and Running Tools**](finding-and-running-tools.md)
- [**Pinned and Recent Items**](pinned-and-recent.md)