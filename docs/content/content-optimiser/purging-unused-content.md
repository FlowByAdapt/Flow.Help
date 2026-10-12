# Purging Unused Content

Use **Purge** to inspect and select supported unused source materials and fill patterns after simulating your proposed cleanup.

---

## Refresh Candidates

1. Finish the parameter, naming, keynote, material and geometry choices.
2. Open **Purge**.
3. Choose **Refresh Purge Candidates**.
4. Wait for the inspection to finish.
5. Review each candidate's **Name**, **Kind** and **Dependent IDs**.

Flow temporarily simulates the current cleanup, checks the supported unused content, then rolls the inspection back without saving changes to the source.

---

## Select Removals

Tick **Remove** for the candidates you approve. **Select All** and **Clear Selection** help manage the displayed selection, but each proposed removal still needs review.

Dependent content must also be selected and within the supported scope. A deletion that would affect unapproved or unsupported content blocks publication.

!!! warning "Refresh after changing the plan"

    Changes to the cleanup plan invalidate the purge review. Refresh candidates and check the removals again before saving.

<!-- SCREENSHOT: Purge tab with selected and retained candidates and the Dependent IDs column visible. -->

---

## Understand Purge Scope

This workflow covers eligible unused source materials and fill patterns. It is not a general purge of family types, geometry, imports, parameters or assets.

Flow rechecks candidates when saving. Newly unused items outside the approved selection remain retained. The report records selected deletions and the remaining Revit unused count.

!!! note "A remaining unused count is not a failed cleanup"

    The count can include content outside this workflow's scope. Read the recorded removals and limitations before deciding whether further manual work is needed.

---

## Related Help

- [**Replacing Materials**](replacing-materials.md)
- [**Reviewing and Saving**](reviewing-and-saving.md)
- [**Troubleshooting**](troubleshooting.md)
