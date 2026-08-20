# Drafting View Extractor Troubleshooting

Use the following checks if Drafting View Extractor cannot process a source file, expected content is not extracted or the extraction cannot be completed.

---

## Library Root Not Found

If Flow displays:

**Library Root Not Found**

the expected content library for the current Revit version could not be found.

Check that:

1. The Flow content library is available from the workstation.
2. The library location is accessible.
3. The library for the current Revit version is present.

Once the library is available, run **Drafting View Extractor** again.

!!! note "Flow uses a version-specific library"

	Drafting View Extractor automatically resolves the content library for
	the current Revit version.

---

## Template Not Found

If Flow displays:

**Template Not Found**

the Revit template required to create the individual drafting-view files could not be found.

The message displays the template path Flow expected to use.

Check that the standard Revit templates for the current Revit version are installed and accessible, then run the extraction again.

---

## A Source File Cannot Be Processed

If one of the selected source files cannot be processed:

1. Confirm that the file is a Revit `.rvt` file.
2. Confirm that the file is accessible from the current workstation.
3. Confirm that the file is located within the configured Flow content library.
4. Review the error displayed by Flow.
5. Correct the reported issue where possible and run the extraction again.

Flow continues processing the batch where possible if an individual source file fails.

---

## An Expected Drafting View Is Missing

If a view you expect to extract does not appear in the extraction preview:

1. Open the source RVT and confirm that the expected view exists.
2. Confirm that the view is a Revit **Drafting View**.
3. Confirm that it is not a view template.
4. Run **Drafting View Extractor** again and review the preview.

!!! info "Drafting view templates are ignored"

	Flow processes non-template Revit Drafting Views from the selected source
	files.

	Other view types and drafting-view templates are not included in the
	extraction.

---

## No Drafting Views Are Found

If Flow reports that no drafting views were found:

1. Confirm that the correct source RVT file was selected.
2. Open the source file and confirm that it contains Drafting Views.
3. Confirm that the required views are not view templates.
4. Try the extraction again.

If another known source file containing drafting views works normally, the issue is likely specific to the original source file.

---

## A Drafting View Was Skipped

A skipped drafting view does not necessarily indicate a problem.

During **Extract Missing / Old Only**, Flow skips an existing extracted file when it was updated within the last seven days.

The extraction preview identifies these views as:

**[EXISTS - RECENT]**

!!! tip "Need to rebuild it anyway?"

	Run the extraction again and select **Force Extract All** if recently
	extracted content needs to be regenerated.

---

## A Drafting View Fails to Extract

An individual drafting view can fail even when other views in the same source file are processed successfully.

At completion, check the **Failed** count and review any errors shown in the extraction summary.

A drafting view must contain drawable content for Flow to create the extracted file.

!!! note "Empty drafting views cannot be extracted"

	If a drafting view contains no drawable elements, Flow cannot create
	reusable drafting content from it.

	Check the source view before trying the extraction again.

---

## Preview Generation Fails

Drafting-view extraction and preview generation are separate stages of the same workflow.

The completion summary reports preview images as:

* **Generated**
* **Skipped**
* **Failed**

If the RVT extraction succeeded but preview generation failed, the extracted Revit content may still have been created successfully.

Review the preview results separately from the extraction results when diagnosing the problem.

---

## Extraction Is Cancelled

The extraction progress can be cancelled while Flow is processing the selected files.

If cancelled, Flow stops the batch workflow rather than continuing into normal completion processing.

Run **Drafting View Extractor** again when you are ready to continue.

---

## Some Files Were Created but Others Failed

Drafting View Extractor processes source files and drafting views individually.

Where possible, a failure affecting one item does not prevent other items from being processed.

When the run completes, review:

* **Files processed**
* **Views found**
* **Created / Updated**
* **Skipped**
* **Failed**

The completion summary also displays the first extraction errors where available.

---

## Reporting a Problem

If the problem continues, record:

* The Revit version.
* The source RVT file being processed.
* The drafting view involved.
* Whether **Extract Missing / Old Only** or **Force Extract All** was used.
* What you expected to happen.
* What happened instead.
* Any error message displayed by Flow.
* A screenshot of the extraction preview or completion summary where useful.

---

## Related Help

* [Drafting View Extractor](index.md)
* [Extracting Drafting Views](extracting-drafting-views.md)
* [Managing Extracted Views](managing-extracted-views.md)