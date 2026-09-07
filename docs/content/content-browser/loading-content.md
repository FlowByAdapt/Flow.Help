# Loading Content

Use Content Browser to load families and drafting views into the active Revit project. Content can be loaded immediately or collected in the load queue.

---

## Before Loading Content

Make sure the project that should receive the content is active.

!!! warning "A project document is required"

    Families and catalogue types cannot be loaded while a family document is active. Switch to the required project before loading.

!!! warning "Existing family values can be overwritten"

    If the family already exists, Flow accepts the incoming library family and allows its family parameter values to overwrite those in the project. The incoming source is also used for shared families.

---

## Load a Standard Family

1. Find and select the required family.
2. Review its preview and project status if required.
3. Click **Load**.

You can also double-click the item or press **Enter** while the content list has focus.

Flow loads the family, refreshes its project status and reports the result in the status strip.

---

## Load a Family with a Type Catalogue

When a matching `.txt` catalogue exists, Flow opens **Select Family Types** instead of loading every type.

1. Select the family and click **Load**.
2. Search or filter the available types.
3. Select one or more types.
4. Click **Load Selected**.

The picker provides:

- multiple selection;
- natural sorting of numbered type names;
- search;
- **Favourites** and **Recent** filters;
- **Select Filtered**;
- **Favourite Selected**;
- **Clear**;
- **Enter** to confirm; and
- **Esc** or **Cancel** to cancel.

**Select Filtered** clears the previous selection and selects every type currently displayed.

Selections and favourite types are remembered separately for each family. **Recent** contains up to 10 types from the most recently confirmed selection for that family.

<!-- SCREENSHOT: Select Family Types.
Show a searched list with favourite, recent and selected types, plus the selection summary and action buttons. -->

---

## Load a Drafting View

1. Find the required drafting view.
2. Select it and click **Load**.

Flow creates a new drafting view, copies the source elements, scale and detail level, and then activates the loaded view.

If its name already exists, Flow adds `(1)`, `(2)` and so on. Existing destination types are retained when duplicate type names are encountered.

Only populated, non-template drafting views can be loaded. The target project must contain a drafting-view type.

---

## Load Multiple Selected Items

A direct multi-selection can contain standard families and drafting views.

Direct batch loading stops before execution if any selected family requires type-catalogue choices. Load those families individually or select their required types before adding them to the queue.

---

## Add Content to the Load Queue

1. Select one or more items.
2. Click **Add To Queue**.
3. Continue finding and adding content.
4. Click **Load Queue** to review the queue.

The queue accepts standard families, selected catalogue types and drafting views. For a single catalogue family, the type picker opens before the types are added.

Duplicate family/type combinations and duplicate drafting views are not added again.

---

## Review and Load the Queue

The queue window shows each item's name, kind, category and source path.

Available actions are:

- **Remove Selected** — remove selected rows and retain the others;
- **Clear Queue** — request removal of queued content;
- **Close** — retain the queue without loading; and
- **Load All** — load the remaining items.

Queue items are processed sequentially. Processing stops at the first failure. Content loaded before that failure remains in the project, and the queue is retained so the result can be reviewed.

The queue is cleared automatically only when the complete load succeeds.

!!! warning "Current Clear Queue limitation"

    The current **Clear Queue** implementation clears queued family items but may leave drafting views queued. Open **Load Queue** to confirm its contents before continuing.

<!-- SCREENSHOT: Load Queue.
Show a standard family, catalogue type and drafting view together. -->

---

## After Loading

Content Browser refreshes family status after a successful family load. Use **Loaded**, **In Use** or **Unused** to review project families.

Drafting-view loading changes the active Revit view to the newly created drafting view.

---

## Getting Help

Hover over **Browser** on the Flow ribbon and press **F1** to open the Content Browser help.

---

## Related Help

- [**Content Browser**](index.md)
- [**Browsing and Searching**](browsing-and-searching.md)
- [**Project Content**](project-content.md)
- [**Content Actions**](content-actions.md)
- [**Content Browser Tools**](content-browser-tools.md)
- [**Troubleshooting**](troubleshooting.md)
