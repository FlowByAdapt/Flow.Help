# Browsing and Searching

Use Content Browser to find approved Revit content by searching the indexed library or combining the available filters.

---

## Open Content Browser

On the Revit ribbon:

**Flow → Content → Browser**

---

## Search for Content

Search filters the displayed content as you type.

1. Click in **Search content...**.
2. Enter a recognisable part of the content name, category, kind, type or indexed path.
3. Review the matching items.
4. Select an item to inspect its preview and information.

You do not need to enter the complete family name. Results beginning with the search text are ranked first.

When a search is entered while the initial **Architecture | Windows** category is selected, Content Browser changes the category to **All Categories** automatically.

!!! tip "Start with a distinctive term"

    A short, recognisable part of the content name is usually enough. Add more text if too many results remain.

---

## Filter by Category

1. Open the **Category** list.
2. Select the required category.
3. Review the filtered content.
4. Select **All Categories** to remove the category restriction.

Categories are generated from the content that passes the current indexing and classification rules. Grouped labels can appear as **Primary Category | Browser Category**, for example **Architecture | Windows**.

---

## Filter by Project Status

The **Project Status** filter compares indexed family names with families in the active Revit document.

| Filter | Shows |
| --- | --- |
| **All** | All content matching the other active filters |
| **Loaded** | Families with one or more loaded types |
| **Not Loaded** | Families not detected in the active document |
| **In Use** | Loaded families with one or more detected family instances |
| **Unused** | Loaded families with no detected family instances |

!!! info "Status follows the active document"

    If you change the active Revit document, its loaded and usage status may differ. Status matching is based on the family name.

---

## Show Favourites

1. Select the required item.
2. Click **Favourite**.
3. Turn on **Favourites** to restrict the list to saved favourites.

A star identifies favourite content. Click **Favourite** again to remove the selected item from favourites.

Favourites are saved for the current Windows user and are not stored in the Revit project.

---

## Show Recent Content

Turn on **Recent** to restrict the list to content recorded as recently loaded. Recent items are also labelled in the content list.

Flow stores up to 20 recent items for the current Windows user.

!!! note "Recent content and batch loading"

    A batch or queued load may not mark every successfully loaded item as recent. Use project status to confirm what is loaded.

---

## Combine Filters

Search and filters work together. You can, for example:

- show only loaded window families;
- search within favourites;
- show unused content within a category; or
- turn on both **Favourites** and **Recent** to show items belonging to either group.

If nothing appears, remove one filter at a time to identify the restriction excluding the item.

<!-- SCREENSHOT: Combined filters.
Show search, category, project status and Favourites or Recent applied to a realistic result list. -->

---

## Review Selected Content

Depending on the item, the Browser can show:

- preview image;
- display and source filename;
- shortened source location;
- content type and family kind;
- project status;
- source, resolved and active load paths;
- load readiness and validation;
- local mirror availability; and
- type-catalogue paths, source and validation.

!!! info "A preview is optional"

    A missing preview does not necessarily mean that the source content is unavailable.

---

## Content Still Does Not Appear

Use **Rebuild Index** after library content changes. If the file still does not appear, it may be in an excluded folder, use an unsupported classification or fail the current naming rules.

See [**Troubleshooting**](troubleshooting.md#recently-added-library-content-is-missing).

---

## Next Step

Continue to [**Loading Content**](loading-content.md), or see [**Content Actions**](content-actions.md) for the selected item's right-click menu.

---

## Getting Help

Hover over **Browser** on the Flow ribbon and press **F1** to open the Content Browser help.

---

## Related Help

- [**Content Browser**](index.md)
- [**Loading Content**](loading-content.md)
- [**Project Content**](project-content.md)
- [**Content Actions**](content-actions.md)
- [**Troubleshooting**](troubleshooting.md)
