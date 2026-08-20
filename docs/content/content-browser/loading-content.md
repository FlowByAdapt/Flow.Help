# Loading Content

Use Content Browser to load families and drafting views into the active Revit project.

Content can be loaded immediately or added to the load queue for later loading.

---

## Before Loading Content

Make sure the Revit project that should receive the content is active.

Content Browser loads content into the **active Revit project**.

!!! info "A project document is required"

    Revit family content cannot be loaded while a family document is active. Switch to the required project before loading.

---

## Load a Family

For a standard family without a type catalogue:

1. Find the required family.
2. Select it in Content Browser.
3. Review the preview and project status if required.
4. Click **Load**.

You can also double-click the selected item or press **Enter** while the content list has focus.

Flow loads the family into the active project and refreshes its project status.

---

## Load a Family with a Type Catalogue

If a matching type catalogue is available, Content Browser opens the type-selection window instead of loading every type automatically.

1. Select the required family.
2. Click **Load**.
3. Search or review the available family types.
4. Select one or more required types.
5. Click **Load Selected**.

Only the selected catalogue types are loaded.

### Type Selection Tools

The type picker supports:

- selecting multiple types;
- searching/filtering the available types;
- **Select Filtered**;
- **Clear Selection**;
- favourite types;
- recent types;
- remembered selections from the previous use of that family;
- **Enter** to confirm;
- **Esc** to cancel.

!!! tip "Selections are remembered"

    When you return to the same type-catalogue family, Content Browser restores the previously selected types and your saved favourites.

---

## Load a Drafting View

Drafting-view content can also be loaded through Content Browser.

1. Find the required drafting view.
2. Select it.
3. Click **Load**.

Flow copies the selected drafting view into the active project.

---

## Add Content to the Load Queue

Use the queue when you want to collect several items before loading them.

1. Select one or more content items.
2. Click **Add To Queue**.
3. Continue finding and adding content as required.
4. Click **Load Queue** to review the queued items.

The queue can contain standard family items and drafting views.

For a single family with a type catalogue, **Add To Queue** first opens the type picker so you can choose the required types.

Duplicate items are not added again.

---

## Review the Load Queue

Click **Load Queue** to open the queue window.

From the queue you can review the collected content and remove unwanted items before loading.

When ready, load the queued content into the active project.

If the load completes successfully, the queue is cleared.

Use **Clear Queue** from the main Content Browser when you want to discard the queued family items without loading them.

!!! warning "Multiple type-catalogue families"

    Loading a multi-selection that requires catalogue choices is not currently available as a single direct batch operation.

    Load those families individually, or select the required catalogue types before adding them to the queue.

---

## After Loading

Successfully loaded content is recorded as **Recent** and the Browser refreshes the family status against the active project.

You can then use the **Project Status** filter to show content that is Loaded, In Use or Unused.

---

## Related Help

- [**Content Browser**](index.md)
- [**Browsing and Searching**](browsing-and-searching.md)
- [**Project Content**](project-content.md)
- [**Content Actions**](content-actions.md)
- [**Troubleshooting**](troubleshooting.md)