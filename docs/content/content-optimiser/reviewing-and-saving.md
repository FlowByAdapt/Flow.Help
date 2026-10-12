# Reviewing and Saving

Use **Review** to approve the combined plan and save a separate cleaned family with a cleanup report.

---

## Review the Complete Plan

1. Choose **Review & Save…**.
2. Read the proposed changes and output options.
3. Expand **Details and audit notes** for additional evidence and limitations.
4. Check names, keynotes, material mappings, connector choices and selected purge items.
5. Resolve any readiness or validation messages.

!!! tip "Review across tabs"

    Changes on different tabs are saved together. Check the whole plan, including choices made earlier in the session.

---

## Complete the Confirmations

Where shared metadata cleanup requires it, check its external usage before selecting **I checked external usage of shared metadata.**

After reviewing the complete plan, select **I approve these changes and will test the cleaned family.**

Changes to the plan reset confirmation. Readiness messages explain why saving is unavailable.

<!-- SCREENSHOT: Review tab showing a combined plan, Details and audit notes, confirmations and Save Cleaned Copy. -->

---

## Save the Cleaned Copy

1. Choose **Save Cleaned Copy**.
2. Select a new output location and filename.
3. Wait for cleanup, validation and reopen checks to complete.
4. Read the result before using the output.

The output is saved in the running Revit version. Existing output files are not replaced; choose a new name or location if a destination is already present.

Flow checks the approved changes and retained state before saving and after reopening. Requested PNG output is part of the publication checks.

!!! warning "Keep the source and report"

    Retain the original family and the cleanup report with the reviewed output. A successful save still requires practical testing of the family's intended behaviour.

---

## Find the Output and Report

Use **Output Folder** to open the saved location. Use **Cleanup Report** to inspect the change report.

**Export Report** is a separate audit-report action; it does not create a cleaned family.

---

## Test Before Library Use

In a disposable project:

1. Load the cleaned family.
2. Place and flex the required types.
3. Check geometry, hosting and retained controls.
4. Inspect material appearance and assignments.
5. Check keynotes, tags and schedules where relevant.
6. Check service connections if the family needs them.
7. Review any accompanying type catalogue against the final names and parameters.

The tool does not automatically replace the family in the production project or update external catalogue/keynote files.

---

## Related Help

- [**Content Optimiser**](index.md)
- [**Purging Unused Content**](purging-unused-content.md)
- [**Troubleshooting**](troubleshooting.md)
