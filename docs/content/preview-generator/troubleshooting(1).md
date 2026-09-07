# Preview Generator Troubleshooting

Use the following checks if Preview Generator cannot process content or an expected preview image is not created.

---

## No Content Is Processed

Confirm that the selected folder contains supported Revit content.

Preview Generator searches the selected folder and all its subfolders for:

- Revit family files (`.rfa`).
- Revit project files (`.rvt`).

Other file types are ignored.

If no supported files are found, Flow displays a completion summary containing zero counts.

---

## A Preview Is Skipped

Preview Generator checks for an existing PNG before opening each Revit file.

The expected PNG must be beside the source file and use the same base filename.

For example:

```text
ADa_Door.rfa
ADa_Door.png
```

Because `ADa_Door.png` already exists, `ADa_Door.rfa` is skipped.

!!! info "Skipped does not mean failed"

    Skipped content is reported separately from failed content.

    A skipped item normally means that the expected PNG filename already
    exists beside the source Revit file.

Flow does not check the existing preview’s age or contents.

---

## I Need to Regenerate an Existing Preview

Normal folder processing preserves existing PNG files.

To regenerate a preview:

1. Locate the PNG beside the source Revit file.
2. Move, rename or remove the existing PNG.
3. Run **Preview Generator** again.
4. Select the folder containing the source Revit file.
5. Allow Flow to generate the replacement preview.

There is currently no force-overwrite option in the Preview Generator folder workflow.

!!! warning "Check the file before removing it"

    Make sure you are removing the preview PNG rather than its source `.rfa`
    or `.rvt` file.

---

## The Processed Count Includes Skipped Files

The completion summary’s **Processed** value represents the total number of supported items found in the batch.

This total includes:

- Successfully generated previews.
- Skipped items.
- Failed items.

Use the separate **Succeeded**, **Skipped** and **Failed** values to understand the result.

---

## A Family Preview Fails

Preview Generator must be able to open the family in the current version of Revit.

If a family fails:

1. Confirm that the `.rfa` file still exists.
2. Confirm that the file is accessible and not locked.
3. Confirm that it can be opened in the current version of Revit.
4. Confirm that you can create files in the source folder.
5. Try opening the family manually.
6. Run Preview Generator again.

A file with an `.rfa` extension must open as a valid Revit family document.

Opening or upgrading some family files may take longer than others.

---

## A Drafting View Preview Fails

Preview Generator attempts to process discovered `.rvt` files as drafting-view content containers.

The file must contain at least one non-template Revit drafting view.

If a drafting-view preview fails:

1. Open the RVT file.
2. Confirm that it contains a Drafting View.
3. Confirm that the view is not a view template.
4. Confirm that the file and its folder are accessible.
5. Run Preview Generator again.

If no suitable drafting view is found, the item is reported as failed.

For help creating suitable content, see:

➡️ [**Drafting View Extractor**](../index.md)

---

## An RVT Contains More Than One Drafting View

Preview Generator uses the first non-template drafting view when the views are ordered alphabetically by name.

It does not create a separate PNG for every drafting view in the same RVT.

For predictable results, use an extracted drafting-view container containing one reusable drafting view.

---

## The Preview PNG Cannot Be Created

The PNG is saved in the same folder as its source Revit file.

If export fails, check that:

1. The source folder is accessible.
2. You have permission to create and replace files in that folder.
3. The expected PNG is not open or locked by another application.
4. The folder is available locally if it is synchronised through a cloud or document-management service.
5. There is sufficient available storage.

When generating a new preview, Flow must be able to create the PNG in the source folder.

---

## Some Content Succeeds and Other Content Fails

Preview Generator handles each supported file separately.

If an individual item fails, Flow records the failure and continues with the remaining files.

The completion summary reports:

- **Succeeded**
- **Skipped**
- **Failed**

The summary reports aggregate counts and does not list the individual failure messages.

If you need to identify a problematic file, process a smaller folder or temporarily isolate the suspected content.

---

## Preview Generator Appears to Pause

Revit may take time to open or upgrade an individual family or drafting-view file.

During this operation, Preview Generator may appear to pause while Revit finishes opening the current file.

Allow the current file time to finish opening before assuming the batch has stopped.

The progress message may display:

```text
Opening / upgrading family. Revit may pause here...
```

or:

```text
Opening / upgrading drafting container. Revit may pause here...
```

---

## Cancel Preview Generation

Use the cancel control in the progress window to stop the batch.

Cancellation is checked before Preview Generator starts the next file. The current file may therefore finish before the batch stops.

Content generated before cancellation remains available.

The completion summary reports:

```text
Cancelled: True
```

---

## Reporting a Problem

If the problem continues, record:

- The Revit version.
- The affected `.rfa` or `.rvt` file.
- The selected content folder.
- Whether a same-named PNG already existed.
- What you expected to happen.
- What happened instead.
- Any Revit or Flow error message.
- The completion summary.
- A screenshot where useful.

Because the completion summary shows counts rather than individual failure details, also record the file being processed when the problem occurred if known.

---

## Related Help

- [Preview Generator](index.md)
- [Generating Preview Images](generating-previews.md)
- [Content Browser](../content-browser/index.md)
- [Drafting View Extractor](../index.md)
