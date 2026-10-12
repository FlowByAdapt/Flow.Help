# Content Optimiser Troubleshooting

Use these checks when auditing, proposing changes or saving a cleaned family does not behave as expected.

---

## I Cannot Find Content Optimiser

Look for **Content Optimiser** in the Content tools or Command Palette. Confirm that your installed Flow build includes the tool.

---

## The Family Will Not Audit

1. Confirm that the file is a saved, accessible `.rfa`.
2. Close that family if it is already open in Revit.
3. Confirm that the running Revit version can open the source.
4. Read the exact status or error message and retry after resolving it.

If the source changes after auditing, audit it again before saving.

---

## A Parameter Cannot Be Cleared, Removed or Renamed

Read **Eligibility / protection**, **Rename availability** and **Evidence**. Built-in, shared-name, formula, reporting, association and office-protection rules can restrict different actions.

Check whether the requested action is supported for the parameter's data type. Keep protected parameters when their dependencies cannot be resolved within this workflow.

---

## Cleanup Affects More Than the Selected Type

The inspection selector controls the displayed type. Text clearing applies across family types, and parameter removal affects the whole family.

!!! warning "Review family-wide actions"

    Use **Keep Selected** to withdraw unwanted parameter actions before saving. Selecting a different inspection type does not change their scope.

---

## A Proposed Name Blocks Saving

Check for empty, invalid or conflicting final names. Review **Type Names** and **Parameter Names**, including protected-name explanations. Correct the proposal or restore the original name.

---

## A Keynote Cannot Be Assigned

Choose a code from the bundled office list. Confirm that the family has a supported editable type keynote parameter. Missing, instance, protected, read-only or formula-driven parameters can prevent assignment.

If a saved code does not resolve to a description in the project, check the project's keynote file and matching code.

---

## Project Replacements Are Missing or Have Changed

Activate the project containing the required materials and audit again. When applying a mapping, keep the project used for the audit active.

If a replacement changed after auditing, repeat the audit and review the mapping against the current material definition.

---

## Propose Replacement Is Rejected

Check that the source has supported editable defaults or direct assignments. Nested/imported internals and protected-only uses cannot establish a writable mapping.

If a material with the target name already exists in the family, select another approved target or resolve the definition conflict separately and audit again.

---

## The Original Material Is Still Present

Mapping updates supported uses; it does not automatically delete the original material. Retained nested/imported uses or protected defaults may still need it.

Inspect the coverage details and cleanup report. Use **Purge** only if the original is offered as an eligible unused candidate after the cleanup simulation.

---

## Material Transfer or Load-back Testing Fails

Read the transfer report for unsupported assets or conflicting definitions. Review **Advanced material options** where the message identifies a thermal-asset conflict.

Resolve the definition or choose another approved material before retrying. Carry out load-back testing in a disposable project.

---

## Geometry Counts Are Partial or Vary Between Types

Read the **Coverage** information. Partial measurements are lower bounds. Use **Compare All Types** to inspect type differences, then review the selected type's elements.

A high rating identifies content for inspection; it does not make geometry eligible for automatic removal.

---

## A Preview Shows Unexpected Content

Confirm the inspection type and inspect the saved family. Temporary preview visibility hides supported reference hosts and connectors; an ambiguous host can remain visible.

Record the family/type and a screenshot if framing or visibility still appears incorrect. Do not delete suspected host geometry just to change the preview.

---

## Purge Candidates Are Missing or Out of Date

Choose **Refresh Purge Candidates** after finishing the other cleanup choices. A plan change requires another refresh.

The list covers supported unused source materials and fill patterns. An empty list can mean there are no eligible candidates, even if Revit reports other unused content.

---

## A Purge Selection Blocks Saving

Review **Dependent IDs** and the status message. Required dependent items must also be approved and supported. A deletion outside the approved scope blocks publication.

Deselect the affected candidate or revise the supported selection, refresh where required, and review the new plan.

---

## Save Cleaned Copy Is Unavailable

1. Confirm that a family has been audited and a change or output option selected.
2. Read the readiness message in **Review**.
3. Resolve invalid names, keynote actions or blocked material mappings.
4. Refresh an invalidated purge review.
5. Complete the required review confirmations again after changing the plan.

---

## Saving Fails or No Successful Output Is Published

Read the error for a source/project change, validation failure, unsupported deletion or output problem. Confirm the destination is writable and choose new filenames when output files already exist.

If the requested PNG fails, resolve the preview issue or remove that option and review the revised plan before retrying.

!!! note "Check the result message"

    Treat the output as ready only after Flow reports a successful save. A failed cleanup or validation is not an approved cleaned family.

---

## Metric Display Appears Different After Loading

The option changes family unit display, not physical size. Project units and custom dimension overrides can control the displayed result. Check the exact dimensions and destination project settings.

---

## Still Having Problems?

Record:

- Revit and Flow versions;
- the source family and inspected type;
- the active project, where material mapping is involved;
- the operation and proposed actions;
- the exact readiness, status or error message;
- expected and actual results;
- the audit or cleanup report, if available.

Include a screenshot of the affected tab and any message window. Provide a sample family where sharing permissions allow it.

---

## Related Help

- [**Content Optimiser**](index.md)
- [**Cleaning Parameters**](cleaning-parameters.md)
- [**Replacing Materials**](replacing-materials.md)
- [**Purging Unused Content**](purging-unused-content.md)
- [**Reviewing and Saving**](reviewing-and-saving.md)
