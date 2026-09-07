# Guided Renumbering

Use **Renumber** when you want to control the order in which Windows, Doors and Curtain Walls are numbered.

Unlike **Standardise**, which repairs invalid or conflicting marks automatically, Renumber is an interactive workflow. Flow works through the project level by level while you pick openings directly in Revit in the order they should be numbered.

---

## Opening Sequences

Renumber maintains four numbering sequences:

| Sequence | Openings |
| --- | --- |
| `W##` | New Windows and Curtain Walls |
| `Wx##` | Existing Windows and Curtain Walls |
| `D##` | New Doors |
| `Dx##` | Existing Doors |

Curtain Walls share the Window sequence.

Demolished openings are not accepted by the Renumber workflow.

➡️ [**Opening Marks**](opening-marks.md)

---

## Start Renumber

From Openings Manager, click **Renumber**.

Flow identifies the project levels containing openings and orders them from the lowest elevation upwards.

Before model selection begins, the start window lets you review the next value for each sequence:

- W
- Wx
- D
- Dx

<!-- SCREENSHOT: Guided Renumber start window showing the four starting counters. -->

---

## Starting Numbers

Flow loads the saved next counters from a previous successful Renumber session where they are available.

Where a saved counter is not available, Flow can derive the next value from the existing project marks.

Review all four starting values before continuing. These values define the beginning of the proposed numbering sequence for the session.

!!! tip "Check all four counters"

    Windows and Curtain Walls share W/Wx, while Doors use D/Dx. A project can therefore be at a different point in each sequence.

---

## Working Plan for Each Level

Renumber processes levels from the lowest elevation upwards.

For each level, Flow looks for a suitable Floor Plan and prefers an opening documentation plan that matches the project's `_Win` naming convention where one is available.

The active working view can therefore change as the workflow advances through the project.

!!! note

    The workflow is level-aware. An opening picked from a different level is rejected rather than being silently added to the current sequence.

---

## Select Openings in Numbering Order

Once the Renumber palette is active, pick openings directly in the Revit model.

The order in which they are selected determines the proposed numbering order.

For example:

```text
First New Window selected   → W01
Second New Window selected  → W02
New Curtain Wall selected   → W03
Next New Window selected    → W04
```

Doors use their own sequence:

```text
First New Door selected   → D01
Second New Door selected  → D02
```

Existing Windows and Curtain Walls use Wx, while Existing Doors use Dx.

Flow displays temporary preview information during the selection process so the proposed sequence can be reviewed before it is written to the model.

<!-- SCREENSHOT: Guided Renumber palette beside a `_Win` Floor Plan with several openings selected and temporary proposed numbering visible. -->

---

## What Can Be Selected?

The interactive picker is restricted to opening elements used by the workflow:

- Windows
- Doors
- Curtain Walls

Flow also validates the opening after it is picked.

A selection is rejected when, for example:

- the opening is on the wrong level
- the opening is Demolished
- it cannot participate in the current numbering workflow

This helps prevent an accidental model pick from corrupting the proposed sequence.

---

## Undo a Selection

Use **Undo Last** when the most recently selected opening should not be part of the current sequence.

Flow removes that selection and recalculates the proposed marks for the remaining openings.

For example, if the current proposed sequence is:

```text
W01
W02
W03
```

undoing the last selection returns it to:

```text
W01
W02
```

You can then continue picking openings.

No mark is committed to the model merely because it appears in the preview.

---

## Move Through the Levels

Complete the required selections on the current level, then use the Renumber palette to advance through the workflow.

Flow continues through the levels containing openings in bottom-up order and activates a suitable working plan where available.

You do not have to select every opening merely to preview a sequence. The important distinction is whether you ultimately **Apply** the proposed numbering.

---

## Apply the Numbering

The proposed marks are not written to the Revit model while you are simply picking openings.

Use **Apply** when you are satisfied with the proposed sequence.

Flow then writes the marks and resolves conflicts within the relevant numbering group.

!!! important "Preview first, Apply second"

    Model picking builds the proposed sequence.

    The opening marks are changed only when the numbering is explicitly applied.

---

## Existing Mark Conflicts

A proposed mark may already belong to another opening in the same numbering group.

When numbering is applied, Flow resolves these conflicts so that the requested sequence does not deliberately leave duplicate marks behind.

Windows and Curtain Walls are resolved within the shared W/Wx group. Doors are resolved within D/Dx.

---

## Cancelling the Session

Pressing **Esc** during the interactive picking workflow cancels the Renumber session without applying the proposed marks.

Because numbering is not committed during normal model picking, cancelling before Apply leaves the proposed sequence unapplied.

Use **Apply** only when you are ready for the marks to be written to the project.

---

## Continuing Later

When a Renumber operation successfully applies changes, Flow stores the next values for:

```text
W
Wx
D
Dx
```

Those counters can then be used as the starting point for a later Renumber session.

The saved counters are updated when numbering changes are actually applied, rather than simply because a preview session was opened.

---

## Curtain Walls

Curtain Walls participate in the Window numbering sequence and do not have a separate counter.

For example:

```text
W01  Window
W02  Curtain Wall
W03  Window
```

Existing Curtain Walls similarly use the Wx sequence.

---

## Demolished Openings

Demolished openings are deliberately excluded from Renumber.

This differs from **Standardise**, which can process Demolished openings using the Existing-style Wx/Dx mark series.

If the project contains Demolished openings, choose the marking workflow with that distinction in mind.

➡️ [**Standardising Openings**](standardising-openings.md)

---

## After Renumbering

After applying the required sequence:

1. Return to the Opening Register.
2. Review the updated marks and statuses.
3. Resolve any remaining opening issues.
4. Continue with opening documentation.

If opening views already existed before the marks were changed, **Standardise** can synchronise opening-view names, while **Conform Views** can perform broader view correction.

➡️ [**Conforming Opening Views**](conforming-opening-views.md)

---

## Standardise or Renumber?

Use **Standardise** when valid existing marks should be retained and Flow only needs to repair invalid or conflicting records.

Use **Renumber** when the actual numbering order matters and you want to establish that sequence by picking openings in the model.

The two commands are complementary rather than interchangeable.

---

## Related Help

- [**Opening Marks**](opening-marks.md)
- [**Standardising Openings**](standardising-openings.md)
- [**Reviewing Openings**](reviewing-openings.md)
- [**Selecting and Locating Openings**](selecting-and-locating-openings.md)
- [**Generating Opening Views**](generating-opening-views.md)
