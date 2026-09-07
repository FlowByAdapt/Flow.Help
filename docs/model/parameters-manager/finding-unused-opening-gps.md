# Finding Unused Opening GPs

Use **Find Unused Opening GPs** to identify Global Parameters whose names match Flow's opening-related naming patterns but for which the current scan detects no association.

You can review a name preview and either leave the candidates unchanged or delete the complete candidate set.

**Ribbon:** Flow → Content → Parameters Manager

---

## Before You Start

Use this workflow only after reviewing the project and confirming that obsolete opening GPs should be removed.

!!! danger "Type-only associations may not be detected"

	The current unused-GP scan checks parameters on non-type elements. A GP used only through a type-parameter association may be classified as unused and offered for deletion.

	Review unfamiliar candidates with **Review Associations** or Revit's native Global Parameters tools before confirming deletion.

---

## Find Unused Opening GPs

1. Open **Parameters Manager**.
2. Expand **Maintenance**.
3. Select **Find Unused Opening GPs**.
4. Wait while Flow scans the current project.
5. Review the candidate count and name preview.

If no candidates are found, Flow reports:

> No unused opening global parameters were found.

No changes are made.

---

## Review the Confirmation

When candidates are found, Flow displays:

- Total number of apparently unused opening GPs
- A preview of up to 30 GP names
- The number of additional candidates when more than 30 are found
- **Yes** and **No** choices

Candidates are ordered alphabetically in the preview.

<!-- SCREENSHOT: Delete Unused Opening GPs confirmation showing the total, alphabetical name preview, Yes and No. If practical, use a case with more than 30 items to show the additional-count message. -->

!!! warning "The list is not individually selectable"

	The confirmation is a preview, not a checklist. **Yes** deletes the complete candidate set found by the cleanup scan. You cannot exclude individual names in this window.

Choose **No** if any candidate requires further investigation.

---

## Which Global Parameters Are Considered

Flow limits the search to GP names beginning with one of its opening-related patterns, including:

- `Window Head Height`
- `X-Window Head Height`
- `Zero Window Sill Height`
- `Architrave`
- `GlassThickness`
- `Ext_Sill`
- `Ext_Trim`
- `Ext Sill`
- `Ext Trim`
- `Exterior Sill`
- `Exterior Trim`
- `Frame Setback`
- `Jamb Liner`
- `Window Glazing`
- `Window Hardware`
- `Window Type`

The name check is case-insensitive and uses the beginning of the GP name. It can therefore include level-specific and wall-type-specific names that continue after the recognised prefix.

This command is not a general cleanup of every unused Global Parameter in the project.

---

## Protected Global Parameters

These exact names are protected and are not offered for deletion:

- `Window Head Height`
- `X-Window Head Height`
- `Zero Window Sill Height`

The protection is case-insensitive.

Names that merely begin with one of those protected names can still be candidates. For example, a level-specific Window Head Height GP is not protected solely because it shares the prefix.

---

## Delete the Candidates

If you have reviewed the candidate set and want to proceed:

1. Select **Yes**.
2. Flow runs the unused-GP check again when the Revit cleanup event executes.
3. Each current candidate is deleted inside one Revit transaction.
4. Review the completion result.
5. The Opening GP Dashboard refreshes automatically.

The completion result reports:

| Result | Meaning |
| --- | --- |
| **Found** | Number of candidates found by the deletion-time scan. |
| **Deleted** | GPs successfully deleted. |
| **Failed** | Candidates that could not be deleted. |

<!-- SCREENSHOT: Unused window GP cleanup completion message showing Found, Deleted and Failed. -->

An individual failure does not prevent other candidates from being deleted. Successfully deleted GPs are committed even when another deletion fails.

---

## Expected Result

After confirmed cleanup:

- Successfully deleted candidate GPs no longer exist in the project
- Protected exact-name GPs remain
- Failed candidates remain
- The dashboard is rescanned automatically

Deleting a GP is different from removing an association. This workflow removes the GP element itself.

---

## Leave the Candidates Unchanged

Select **No** in the confirmation.

The workflow closes without deleting anything. You can then:

1. Use **Review Associations** on representative window instances.
2. Review relevant window types in Revit.
3. Use Revit's native Global Parameters editor.
4. Run the cleanup again after confirming the candidate set.

---

## If an Expected GP Appears in the List

Do not confirm deletion.

Check whether:

1. The GP is associated only with a type parameter.
2. Its intended family instances or types are absent from the current project.
3. Its association was removed unintentionally.
4. It is a level-specific or wall-type-specific GP awaiting use.
5. Its name matches an opening prefix even though it serves another purpose.

---

## Current Limitations

- Type-only associations may not be detected.
- Candidate scope is determined partly by GP-name prefixes.
- The preview does not allow individual candidates to be selected or excluded.
- Confirming deletion processes the complete candidate set found at execution time.
- Individual failures are counted but do not roll back successful deletions.
- The command does not find unrelated unused project GPs.

---

## Related Help

- [Parameters Manager](index.md)
- [Reviewing Global Parameters](reviewing-global-parameters.md)
- [Reviewing Associations](reviewing-associations.md)
- [Removing Associations](removing-associations.md)
- [Native Global Parameter Editor](native-global-parameter-editor.md)
- [Parameters Manager Troubleshooting](troubleshooting.md)
