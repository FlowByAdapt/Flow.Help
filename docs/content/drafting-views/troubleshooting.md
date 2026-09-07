# Drafting View Extractor Troubleshooting

Use these checks when a source cannot be scanned, expected output is missing or extraction does not complete as expected.

---

## Library Root Not Found

Flow resolves the library for the running Revit version. Confirm that the path shown in **Library Root Not Found** exists and is accessible from the workstation.

---

## Template Not Found

Flow expects Autodesk's English `DefaultMetric.rte` for the running Revit version. Confirm that the path shown in **Template Not Found** exists.

---

## A Source Cannot Be Scanned

Before displaying the confirmation, Flow opens every selected file to discover its drafting views. One invalid, inaccessible or unsupported file can interrupt this initial scan.

1. Confirm that each selection is an accessible `.rvt`.
2. Remove uncertain files and retry them individually.
3. Confirm that files are not already locked in a way that prevents background opening.

---

## Source File Is Outside the Library

Mirrored extraction requires every source to be inside the configured version-specific library.

If Flow reports that the source is not inside the library root, move or select the correct centrally managed source before trying again.

---

## An Expected View Is Missing from the Preview

Confirm that the source contains a non-template Revit drafting view. Other view types and view templates are ignored.

The dialogue lists only the first 50 views. Compare the reported total with the visible list before assuming that a later view was not discovered.

---

## No Drafting Views Are Found

1. Confirm that the correct source was selected.
2. Open it and verify that it contains non-template drafting views.
3. Retry the source by itself.

---

## A Recent View Was Skipped

Normal extraction skips an existing output RVT whose last-write time is seven days old or less.

Use **Force Extract All** when the RVT must be replaced immediately.

---

## An Empty Drafting View Failed

Empty views appear during discovery but fail during extraction with **No drawable elements found**.

Add the required drawable content to the source view or exclude that container from the run.

---

## The Extracted RVT Is Empty or Contains the Wrong View

Open the output RVT and inspect its non-template drafting views.

The current final-view cleanup behaviour is under review because the view receiving the copied elements can be deleted before saving. Do not publish an unverified output file.

---

## A Preview Was Skipped

The automatic preview stage skips any output whose matching PNG already exists. This includes RVTs regenerated with **Force Extract All**.

Delete or regenerate the existing PNG when it no longer represents the extracted RVT.

---

## Preview Generation Failed

RVT extraction and PNG generation are separate stages. A successful extracted RVT can remain available even when its preview fails.

Confirm that the output contains a non-template drafting view and review the preview error separately.

---

## Extraction Was Cancelled

Files already created remain in place. Run the extractor again to continue; recent outputs may then be skipped by the seven-day rule.

Cancellation during the final or only source file may still allow preview generation and completion processing to begin. Review the progress and output rather than assuming no further work occurred.

---

## Some Items Succeeded and Others Failed

Per-view failures normally do not prevent later views from being attempted. A source-level error also normally allows the next source file to proceed.

The final Failed total can omit a source-level exception, and Created/Updated can omit successful outputs that purged zero elements. Review earlier error messages and the output folder as well as the summary.

---

## Open Output Folder Does Nothing

This action uses the first valid output path found in the run. It cannot open a folder when no result supplied an output path.

---

## Reporting a Problem

Record:

- Revit and Flow versions;
- source RVT path;
- drafting-view name;
- extraction mode;
- output RVT and PNG paths;
- the displayed status or error;
- expected and actual results; and
- screenshots of the confirmation, progress or completion dialogue.

---

## Getting Help

Hover over **Drafting** on the Flow ribbon and press **F1** to open Drafting View Extractor help.

---

## Related Help

- [**Drafting View Extractor**](index.md)
- [**Extracting Drafting Views**](extracting-drafting-views.md)
- [**Managing Extracted Views**](managing-extracted-views.md)
