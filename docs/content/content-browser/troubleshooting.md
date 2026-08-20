# Content Browser Troubleshooting

Use the following checks if Content Browser is not behaving as expected.

---

## Content Browser Is Not Open

Open Content Browser from the Revit ribbon:

**Flow → Content → Browser**

---

## I Cannot Find the Content I Need

Active filters may be excluding the item.

1. Clear or shorten the current search.
2. Set **Category** to **All Categories**.
3. Set **Project Status** to **All**.
4. Turn off **Favourites** and **Recent** if they are enabled.
5. Search again using a recognisable part of the content name.

If recently added library content is still missing, the content index may need to be rebuilt.

See [**Browsing and Searching**](browsing-and-searching.md).

---

## Recently Added Library Content Is Missing

If a file has been added to the Flow library but does not appear in Content Browser:

1. Confirm that the file is in the correct Revit-version library.
2. Click **Rebuild Index**.
3. Allow the index rebuild to complete.
4. Search for the content again.

If the index cannot be rebuilt, Content Browser reports the index or library path problem in the status area.

---

## A Preview Is Not Available

A missing preview does not necessarily mean that the content itself is unavailable.

You can:

1. Right-click the item.
2. Use **Generate Preview** if available.
3. Use **Regenerate Preview** if an existing preview needs to be recreated.

You can also review the content name, type and path information before loading it.

---

## A Family Will Not Load

Check the following:

1. Make sure the required Revit **project** is active.
2. Confirm that you are not currently working in a family document.
3. Confirm that the source family still exists.
4. Try selecting the item again and review the status message.

Flow reports failures such as a missing family file, an unavailable project document, or a file that does not open as a Revit family.

---

## A Type Catalogue Opens but No Types Are Available

If Flow detects a type catalogue but cannot read any types, loading stops and reports:

**Type catalog detected, but no types could be read.**

The catalogue should be reviewed before trying again.

You can right-click the family and use the available type-catalogue actions to open or edit the catalogue.

---

## I Cancelled the Type Selection Window

Cancelling the type picker does not load the family.

Select the family and click **Load** again when you are ready to choose the required types.

---

## Multiple Selected Families Will Not Load Together

A direct multi-selection that includes content requiring type-catalogue choices is not currently completed as one batch operation.

Load the catalogue families individually, or choose their required types before adding them to the load queue.

---

## The Load Queue Does Not Change

Content Browser avoids adding duplicate queue items.

If the status reports that the queue is unchanged, the selected content may:

- already be in the queue; or
- not be supported by that queue action.

Open **Load Queue** to review what is currently queued.

---

## A Family Does Not Appear as Loaded

The project-status information is based on the active Revit project.

Check that:

1. the correct project is active;
2. the family name matches the indexed library family;
3. the load completed successfully.

After a successful family load, Content Browser refreshes the project status.

---

## Reload Family Is Not Available

**Reload Family** is only available when:

- the selected content is a `.rfa` Revit family; and
- that family is already loaded in the active project.

Use the **Loaded** project-status filter if you want to find families eligible for reloading.

---

## Reload Project Families Finds Nothing

If **Reload Project Families** reports:

**No matching loaded families were found.**

check that:

1. the correct project is active;
2. the expected families are loaded;
3. the appropriate categories were selected;
4. matching family files exist in the current Flow library.

See [**Project Content**](project-content.md).

---

## A Reloaded Family Is Reported as Not Found

Reloading matches the project family name against `.rfa` file names in the current Flow library.

A **Not found** result means Flow could not find a matching library family for that name.

Check the library file name and the Revit version currently running.

---

## Cached Content Appears Out of Date

Use **Clear Cache** when the local Content Browser cache appears inconsistent with the current library.

1. Click **Clear Cache**.
2. Allow the cache to be cleared.
3. Select or load the content again.

Content Browser will resolve the required content again.

---

## Still Having Problems?

If the problem continues, record:

- the content or family involved;
- your Revit version;
- your Flow version;
- the active Revit project;
- the active Content Browser filters;
- what you were trying to do;
- the status or error message shown;
- what you expected to happen;
- what happened instead.

A screenshot of Content Browser and any message window can also help identify the problem.

---

## Related Help

- [**Content Browser**](index.md)
- [**Browsing and Searching**](browsing-and-searching.md)
- [**Loading Content**](loading-content.md)
- [**Project Content**](project-content.md)
- [**Content Actions**](content-actions.md)
- [**Content Browser Tools**](content-browser-tools.md)