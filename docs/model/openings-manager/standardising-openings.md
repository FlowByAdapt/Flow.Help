# Standardising Openings

Use **Standardise** to correct invalid or conflicting opening marks while preserving valid unique marks wherever possible.

Standardise also synchronises opening-view names so that existing documentation remains aligned with the current opening marks.

---

## When to Use Standardise

Use Standardise when:

- the Opening Register reports non-standard marks
- duplicate or conflicting marks need to be resolved
- opening marks have been edited manually
- opening views no longer match their opening marks
- you want to prepare openings before generating documentation

Standardise is intended to **repair the existing marking system**, not replace a deliberate numbering sequence.

If you need to control the order in which openings are numbered, use **Renumber** instead.

➡️ [**Guided Renumbering**](guided-renumbering.md)

---

## Standard Mark Groups

Flow uses the following primary mark conventions:

| Opening | New | Existing |
| --- | --- | --- |
| Window | `W##` | `Wx##` |
| Curtain Wall | `W##` | `Wx##` |
| Door | `D##` | `Dx##` |

Windows and Curtain Walls share the W/Wx numbering group.

Doors use the separate D/Dx numbering group.

➡️ [**Opening Marks**](opening-marks.md)

---

## Standardise from Openings Manager

From the Opening Register:

1. Set any required filters.
2. Check individual openings if you want to build a specific working selection.
3. Click **Standardise**.
4. Choose the required scope.
5. Allow Flow to process the openings.
6. Review the updated register.

Depending on the current register state, the scope can be based on:

- **Checked** openings
- **Filtered** openings
- **All** openings

!!! tip "Build the scope before starting"

    Changing **Category**, **Level**, **Phase** or **GP Status** clears the current checked selection.

    Set the filters first, then check openings or use **Select Filtered** before running Standardise.

<!-- SCREENSHOT: Standardise scope chooser showing the available Checked / Filtered / All choices. -->

---

## What Flow Changes

Standardise reviews each opening in the chosen scope and determines whether its mark needs correction.

Flow preserves valid unique marks where possible.

An opening generally needs a new mark when its current mark:

- does not follow the expected format for its category and phase
- conflicts with another opening in the same numbering group

When a replacement is required, Flow assigns an available number in the appropriate mark group.

This means Standardise does **not** simply start at 01 and renumber every selected opening.

!!! example

    If `W01`, `W02` and `W04` are already valid and unique, Standardise does not renumber them merely to close the gap.

    An opening that requires correction can be assigned an available number without unnecessarily changing the valid marks.

---

## Windows and Curtain Walls Share Numbers

Windows and Curtain Walls are treated as one numbering group.

For example:

```text
W01  Window
W02  Curtain Wall
W03  Window
```

A Window and Curtain Wall using the same W## mark create a conflict that Standardise can resolve.

Doors are checked separately within the D/Dx group.

---

## Demolished Openings

Standardise uses the **Existing-style** mark series for Demolished openings:

| Demolished opening | Standardise mark series |
| --- | --- |
| Window | `Wx##` |
| Curtain Wall | `Wx##` |
| Door | `Dx##` |

This differs from **Renumber**, which does not accept Demolished openings.

!!! important

    If a project contains Demolished openings, Standardise and Renumber should not be treated as interchangeable workflows.

---

## View Name Synchronisation

After mark standardisation, Flow also synchronises opening-view names.

For Windows and Curtain Walls, the view name is based on the opening mark.

Door documentation uses the Door type-based naming convention.

This synchronisation is useful when:

- an opening mark has changed
- an existing elevation still uses an older opening mark
- mark conflicts have been corrected after views were created

!!! info "View synchronisation is part of Standardise"

    Standardise is not only a mark-cleanup command. Existing opening-view names are also checked so that the documentation remains aligned with the current opening information.

For broader repair of existing opening views, use **Conform Views**.

➡️ [**Conforming Opening Views**](conforming-opening-views.md)

---

## If Marks Are Already Standard

Valid unique marks are retained rather than being changed unnecessarily.

This makes Standardise suitable for a project where only part of the opening register requires correction.

If you need a completely new deliberate sequence rather than selective repair, use **Renumber**.

---

## Standardise During Generate Views

**Generate Views** checks the selected scope before creating component opening elevations.

If non-standard openings are found, Flow stops and offers:

- **Standardise Now**
- **Cancel**

If you choose **Standardise Now**, Flow runs Standardise against that scope.

!!! warning "Generate Views does not automatically resume"

    Choosing **Standardise Now** completes the standardisation operation and ends that Generate Views invocation.

    After standardisation has finished, click **Generate Views** again to continue with view generation.

This is deliberate separation between correcting the opening data and generating the documentation.

➡️ [**Generating Opening Views**](generating-opening-views.md)

---

## Standardise or Renumber?

| Use Standardise when… | Use Renumber when… |
| --- | --- |
| Existing valid marks should be retained | You want a deliberate new numbering order |
| Invalid marks need correction | You want to pick openings in sequence |
| Duplicate marks need resolving | You want to work through levels interactively |
| Existing view names need synchronising | You want to establish the W/Wx/D/Dx sequence manually |

The two workflows can be used at different stages of the same project, but they solve different problems.

---

## After Standardising

When Standardise is launched from Openings Manager, the register is refreshed after the operation completes.

Review:

- the corrected marks
- any remaining status issues
- the resulting view names where documentation already exists

Remember that an opening can still show an issue for reasons other than its mark, such as a Global Parameter or other audited condition.

<!-- SCREENSHOT: Opening Register after Standardise, showing corrected W/D marks and clean mark-related statuses. -->

---

## Related Help

- [**Reviewing Openings**](reviewing-openings.md)
- [**Selecting and Locating Openings**](selecting-and-locating-openings.md)
- [**Opening Marks**](opening-marks.md)
- [**Guided Renumbering**](guided-renumbering.md)
- [**Generating Opening Views**](generating-opening-views.md)
- [**Conforming Opening Views**](conforming-opening-views.md)
