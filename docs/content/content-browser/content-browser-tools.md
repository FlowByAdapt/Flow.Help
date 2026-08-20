# Content Browser Tools

Use the **Tools** menu in Content Browser to access additional utilities for project content, sheets, drafting views, family files and library maintenance.

These tools provide supporting workflows that sit alongside the main Content Browser searching and loading functions.

---

## Open Content Browser Tools

Open:

**Flow → Content → Browser**

Then open the **Tools** menu to view the available utilities.

---

## Sheet & Drafting View Utilities

Use **Sheet & Drafting View Utilities** for the integrated sheet and drafting-view operations available through Content Browser.

Select **Sheet & Drafting View Utilities** from the **Tools** menu to open the workflow.

---

## Auto Adjust Crop Regions

Use **Auto Adjust Crop Regions** to automatically adjust crop regions for selected eligible project views.

1. Open **Tools**.
2. Select **Auto Adjust Crop Regions**.
3. Review the available project views.
4. Select the views to process.
5. Run the adjustment.

The selection window groups available views by view type, including:

* Plans
* Sections
* Elevations
* Details

!!! info "Views are collected for selection"

	Flow collects the eligible project views and presents them for selection before making the crop-region adjustments.

	This allows you to choose which views are processed.

---

## Transfer Project Standards

Use **Transfer Project Standards** to start the Flow workflow for transferring selected project standards.

1. Open **Tools**.
2. Select **Transfer Project Standards**.
3. Continue through the Transfer Project Standards workflow.

---

## Reload Project Families

Use **Reload Project Families** to compare loaded project families in selected categories against the current Flow library and reload matching families.

1. Open **Tools**.
2. Select **Reload Project Families**.
3. Choose the family categories to review.
4. Continue through the reload workflow.

For more information, see [**Project Content**](project-content.md#reload-project-families).

!!! info "Families are matched against the Flow library"

	Flow checks the selected project-family categories against the current library so that matching library families can be identified for reloading.

---

## Purge Selected Unused Types

Use **Purge Selected Unused Types** to select and remove unused project types through the Flow purge workflow.

1. Open **Tools**.
2. Select **Purge Selected Unused Types**.
3. Review the available unused types.
4. Select the types you want to purge.
5. Continue with the purge operation.

!!! warning "Review the selection before purging"

	Purging removes the selected unused types from the project.

	Check the selected types before completing the operation.

---

## Sheet Copier

Use **Sheet Copier** to select sheets from a source Revit file and copy them through the Flow workflow.

1. Open **Tools**.
2. Select **Sheet Copier**.
3. Select the required source Revit file.
4. Review the available sheets.
5. Select the sheets to copy.
6. Continue through the Sheet Copier workflow.

---

## Family File Cleanup

Use **Family File Cleanup** to process Revit family files through the Flow cleanup workflow.

1. Open **Tools**.
2. Select **Family File Cleanup**.
3. Select the family files to process.
4. Start the cleanup operation.

Flow displays progress while the selected files are being processed.

!!! info "Progress is shown during processing"

	Flow displays the progress of the cleanup operation while the selected family files are processed.

---

## Clean Revit Backups

Use **Clean Revit Backups** to remove unwanted Revit backup files.

1. Open **Tools**.
2. Select **Clean Revit Backups**.
3. Choose the location or files to process.
4. Review the available cleanup options.
5. Run the cleanup.

!!! warning "Check the cleanup options"

	Review the selected location and cleanup options before starting.

	Backup files removed by the cleanup operation should only be deleted when they are no longer required.

---

## Copy Folder Structure

Use **Copy Folder Structure** to reproduce an existing folder hierarchy at another location without copying the files contained within it.

1. Open **Tools**.
2. Select **Copy Folder Structure**.
3. Select the source folder structure.
4. Select the destination.
5. Run the copy operation.

!!! tip "Use this when only the folders are required"

	Use **Copy Folder Structure** when you need to reproduce an existing folder arrangement without copying the content stored inside those folders.

---

## Rebuild the Content Index

**Rebuild Index** is available from the main Content Browser window rather than the **Tools** menu.

Use it when the Flow content library has changed but the expected content is not appearing in Content Browser.

Select **Rebuild Index** to rescan the current Flow library and rebuild the Content Browser index.

!!! note "Rebuild only when required"

	You do not normally need to rebuild the index each time Content Browser is opened.

	Use **Rebuild Index** when there is a genuine difference between the current library and the content being shown in Content Browser.

---

## Clear the Content Cache

**Clear Cache** is also available from the main Content Browser window.

Use it when locally cached content appears stale or inconsistent with the current Flow library.

Select **Clear Cache** to remove the local Content Browser cache and recreate the cache location.

Content Browser resolves the required content again as it is subsequently selected or loaded.

!!! info "The library itself is not removed"

	Clearing the local Content Browser cache does not remove content from the Flow library.

	It removes the local cached content so that Content Browser can resolve the required library content again.

---

## Related Help

* [**Content Browser**](index.md)
* [**Browsing and Searching**](browsing-and-searching.md)
* [**Loading Content**](loading-content.md)
* [**Project Content**](project-content.md)
* [**Content Actions**](content-actions.md)
* [**Troubleshooting**](troubleshooting.md)

---