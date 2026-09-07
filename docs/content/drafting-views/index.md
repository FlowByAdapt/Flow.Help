# Drafting View Extractor

The **Drafting View Extractor** creates individually managed Revit library files from drafting views held in source RVT containers.

Use it to review one or more source files, process their non-template drafting views and generate matching preview images for Content Browser.

---

## Open Drafting View Extractor

On the Revit ribbon:

**Flow → Content → Drafting**

The command is located in the expanded **Content** panel.

<!-- SCREENSHOT: Ribbon location.
Show the expanded Content panel with Drafting View Extractor visible. -->

---

## Before You Begin

The source RVT files must be located inside the Flow content library for the Revit version currently running.

Flow also requires Autodesk's English `DefaultMetric.rte` template for that Revit version. If either location is unavailable, Flow reports the expected path before extraction begins.

---

## Typical Workflow

1. Open **Drafting View Extractor**.
2. Select one or more source RVT files.
3. Review the drafting views and their output status.
4. Choose normal or forced extraction.
5. Allow Flow to process the RVTs and then generate previews.
6. Review the completion summary.
7. Open the output folder, extract another group or close the workflow.

➡️ [**Extracting Drafting Views**](extracting-drafting-views.md)

---

## What Do You Want to Do?

### Extract Drafting Views

Select source RVT files, review what Flow finds and create or update reusable content.

➡️ [**Extracting Drafting Views**](extracting-drafting-views.md)

### Manage Extracted Views

Understand where extracted files are stored, how they are named and how the seven-day update rule works.

➡️ [**Managing Extracted Views**](managing-extracted-views.md)

### Resolve a Problem

Find help for missing libraries or templates, source-file failures, skipped content, cancellation and preview problems.

➡️ [**Troubleshooting**](troubleshooting.md)

---

## Important Current Limitations

- The confirmation dialogue lists no more than the first 50 discovered views.
- Existing PNG previews are skipped, even when **Force Extract All** regenerates the corresponding RVT.
- Generated RVTs should be checked before publishing while the current extracted-view retention behaviour is being verified.

---

## Getting Help

Hover over **Drafting** on the Flow ribbon and press **F1** to return directly to this page.

---

## Related Help

- [**Extracting Drafting Views**](extracting-drafting-views.md)
- [**Managing Extracted Views**](managing-extracted-views.md)
- [**Troubleshooting**](troubleshooting.md)
