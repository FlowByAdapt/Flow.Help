# Content Optimiser

**Content Optimiser** helps prepare Revit families for office use. Audit a saved family, review its parameters and geometry, propose supported changes, and save a separate cleaned copy with a report.

Use it to remove unwanted metadata, clear eligible text values, improve type and parameter names, assign office keynotes, replace supported material assignments and review unused materials and fill patterns.

---

## Open Content Optimiser

Find the tool in Flow's **Content** tools or through the **Command Palette**.

Open the project containing your approved replacement materials before auditing if you intend to use material mapping.

<!-- SCREENSHOT: Audited family in the final tool window. Show the preview, Values / inspection type selector, workflow tabs and top action buttons. -->

---

## Understand the Window

The left-hand area contains the family preview, summary and **Values / inspection type** selector. The main tabs contain the proposed changes:

| Tab | Purpose |
| --- | --- |
| **Parameters** | Review eligibility and propose metadata removal or text clearing. |
| **Type Names** | Review and edit proposed family type names. |
| **Parameter Names** | Rename eligible family parameters. |
| **Keynotes** | Assign office keynote codes to supported types. |
| **Materials** | Map supported family material uses to project replacements. |
| **Geometry** | Inspect complexity, compare types and choose connector, unit-display and PNG options. |
| **Purge** | Review and select supported unused materials and fill patterns. |
| **Review** | Check the combined plan and save the cleaned copy. |

---

## First-Time Workflow

1. Choose **Select Family and Audit** and select a saved `.rfa` file.
2. Review the family summary, types and audit notes.
3. On **Parameters**, generate a cleanup proposal or select actions manually.
4. Review names, keynotes and material replacements where required.
5. Inspect **Geometry** and choose any output options.
6. If purging, refresh candidates after finishing the other changes and select the required removals.
7. Choose **Review & Save…** and check the complete plan.
8. Complete the required review confirmations and choose **Save Cleaned Copy**.
9. Read the cleanup report and test the output in a separate project.

!!! tip "Start with a small plan"

    For your first family, make a few easy-to-check changes. Inspect the saved result before using a wider cleanup plan.

---

## Important Limitations

The tool works with one external loadable family at a time. It saves a separate output and does not automatically replace families in your project.

An audit cannot establish whether external tags, schedules or office automation depend on a shared parameter. Geometry ratings help identify content for inspection; they do not prove that an element is safe to remove or predict a percentage performance improvement.

Nested family internals, imported geometry and general geometry simplification are outside the supported cleanup scope. Material replacement coverage must be reviewed for each family.

---

## What do you want to do?

### Inspect a Family

Select a saved family, inspect type values and understand audit evidence.

➡️ [**Selecting and Auditing Families**](selecting-and-auditing.md)

### Clean Up Metadata

Review suggested actions, preserve required information and clear or remove eligible parameters.

➡️ [**Cleaning Parameters**](cleaning-parameters.md)

### Improve Names

Review naming suggestions and rename eligible types and parameters.

➡️ [**Renaming Types and Parameters**](renaming.md)

### Assign Office Keynotes

Apply an approved keynote to selected types or all supported types.

➡️ [**Assigning Keynotes**](assigning-keynotes.md)

### Use Approved Materials

Review supported material uses and propose project material replacements.

➡️ [**Replacing Materials**](replacing-materials.md)

### Inspect Geometry and Choose Output Options

Compare complexity between types and review connectors, metric display and preview output.

➡️ [**Geometry and Output Options**](geometry-and-output-options.md)

### Remove Supported Unused Content

Inspect and select unused materials and fill patterns after the proposed cleanup.

➡️ [**Purging Unused Content**](purging-unused-content.md)

### Save a Reviewed Copy

Review the combined plan, save a separate family and check its report.

➡️ [**Reviewing and Saving**](reviewing-and-saving.md)

### Having Problems?

Find checks for blocked actions, material mappings, purge reviews and output failures.

➡️ [**Troubleshooting**](troubleshooting.md)
