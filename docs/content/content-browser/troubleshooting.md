# Content Browser Troubleshooting

Use these checks when Content Browser is not behaving as expected.

---

## Content Browser Does Not Open

Open it from:

**Flow → Content → Browser**

An active Revit document is required. Confirm that the version-specific Flow library exists and is available through SharePoint, and that Flow can read or create `content_index.json`.

---

## I Cannot Find the Content I Need

1. Clear or shorten the search.
2. Set **Category** to **All Categories**.
3. Set **Project Status** to **All**.
4. Turn off **Favourites** and **Recent**.
5. Search using a recognisable part of the name.

If the item was recently added, rebuild the index.

---

## Recently Added Library Content Is Missing

1. Confirm that the file is in the library for the running Revit version.
2. Confirm that it is `.rfa`, `.rvt` or `.rte`.
3. Click **Rebuild Index** and wait for **Content index rebuilt.**
4. Search again with all filters cleared.

If it remains missing, the file may be deliberately excluded or may not match a classification rule. Archive folders, Revit backup files, nested/NST content, some detail content and unclassified families are excluded.

---

## A Preview Is Not Available

A missing preview does not prevent loading when the Revit source is valid.

Right-click the item and use **Generate Preview** or **Regenerate Preview** where appropriate. Preview generation supports `.rfa` and `.rvt`, not `.rte`.

---

## Cached Content Appears Out of Date

Cached files are copied only when the local version does not already exist.

1. Click **Clear Cache**.
2. Select or load the item again.
3. Flow copies the current family and any matching catalogue/preview back into the cache.

Clearing the cache does not delete the source library.

---

## A Family Will Not Load

Check that:

1. the required project is active;
2. a family document is not active;
3. the source family exists;
4. the library or cached path is available; and
5. the status strip does not report a catalogue mismatch or missing file.

---

## A Type Catalogue Contains No Available Types

If Flow reports **Type catalog detected, but no types could be read**, review the `.txt` catalogue before trying again.

The catalogue and family must be in the same folder and use the same base filename. Use the right-click catalogue actions to open or edit it.

---

## Type Selection Was Cancelled

Closing the picker, pressing **Esc**, or confirming without a usable selection prevents loading. Select the family and click **Load** again.

---

## Multiple Selected Families Will Not Load Together

Direct batch catalogue selection is not currently connected. Load catalogue families individually or select their types while adding them to the queue.

---

## The Load Queue Does Not Change

The selected item may already be queued or may not be supported by the queue action. Open **Load Queue** to review its current contents.

If **Clear Queue** leaves drafting views behind, remove them through the queue window before loading.

---

## A Queued Load Failed Partway Through

Queue processing stops at the first failure. Items processed earlier can already be loaded into the project; remaining items are not attempted and the queue is retained.

Review the result, confirm project status and remove or correct the failed item before retrying.

---

## A Family Does Not Appear as Loaded

Status is based on the active document and case-insensitive family-name matching.

Confirm that the correct project is active, the family name matches the indexed filename or family name, and loading completed successfully.

---

## Reload Family Is Not Available

The selected item must show as loaded. The command then verifies that it is an `.rfa` family and that a family name and library path are available.

Use the **Loaded** filter to find likely candidates.

---

## Reload Project Families Finds Nothing

Confirm that:

1. the correct project is active;
2. expected families are loaded;
3. appropriate categories were selected; and
4. matching `.rfa` filenames exist in the current library.

---

## Sheet Copier Finds No Sheets

Confirm that the selected source is an accessible `.rvt` project containing non-placeholder sheets.

The discovery workflow returns the same empty result when no sheets exist and when the source project cannot be opened.

---

## Family Cleanup Overwrites an Output File

Cleaned families are saved directly into the output folder with overwrite enabled. Source subfolders are not currently reproduced.

Use an empty output folder and ensure that selected source families do not share filenames.

---

## Backup Files Cannot Be Deleted

A file may be open, locked, read-only beyond the attributes Flow can normalise, unavailable through SharePoint or protected by permissions.

Failed files remain in the scan results after the deletion attempt.

---

## Still Having Problems?

Record:

- the content or file involved;
- Revit and Flow versions;
- the active document;
- active Browser filters;
- the operation being attempted;
- the exact status or error message;
- the expected result; and
- the actual result.

Include a screenshot of Content Browser and any message window where possible.

---

## Getting Help

Hover over **Browser** on the Flow ribbon and press **F1** to open the Content Browser help.

---

## Related Help

- [**Content Browser**](index.md)
- [**Browsing and Searching**](browsing-and-searching.md)
- [**Loading Content**](loading-content.md)
- [**Project Content**](project-content.md)
- [**Content Actions**](content-actions.md)
- [**Content Browser Tools**](content-browser-tools.md)
