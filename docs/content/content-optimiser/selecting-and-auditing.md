# Selecting and Auditing Families

Audit a family before choosing cleanup actions. The audit records its types, parameters, materials, dependencies and geometry information.

---

## Before You Begin

Use a saved, accessible `.rfa` file that the running Revit version can open. Close that family in Revit before selecting its saved copy.

If replacing materials, activate the project containing the approved materials first. Keep that project available for the subsequent mapping and save operations.

---

## Select a Family

1. Open Content Optimiser.
2. Choose **Select Family and Audit**.
3. Select the required `.rfa` file.
4. Wait for the audit to finish.
5. Review the summary and status messages.

The source is inspected without saving cleanup changes to it.

---

## Review Type Values

Use **Values / inspection type** to select the type you want to inspect. Review its displayed parameter values and geometry information.

!!! warning "Inspection type does not limit cleanup"

    Clearing eligible text applies across all family types. Removing a parameter removes its definition from the whole family. Selecting one inspection type does not restrict those actions to that type.

<!-- SCREENSHOT: Type selector and Parameters grid showing values, eligibility, formula and evidence columns. -->

---

## Understand Audit Evidence

On **Parameters**, review **Eligibility / protection**, **Formula** and **Evidence** before selecting an action. A detected dependency or office protection can prevent a change.

On **Materials**, inspect the selected material details and supported assignment counts. On **Geometry**, review the measurement coverage and nested-family information.

!!! note "Internal evidence has limits"

    The audit checks evidence available inside the family. Check external tags, schedules, exports and office workflows separately before changing shared metadata.

---

## Export or Clear the Audit

Use **Export Report** to save the audit as a JSON report. This records the inspection and does not save a cleaned family.

Use **Close Family** to clear the current family and proposal before starting another audit.

---

## Related Help

- [**Content Optimiser**](index.md)
- [**Cleaning Parameters**](cleaning-parameters.md)
- [**Geometry and Output Options**](geometry-and-output-options.md)
- [**Troubleshooting**](troubleshooting.md)
