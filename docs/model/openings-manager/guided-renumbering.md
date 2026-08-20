# Guided Renumbering

Use **Guided Renumber** when you want to control the order in which windows, doors and curtain walls are numbered.

Rather than automatically correcting existing marks, Flow guides you through the project level by level while you select openings directly from the Revit model.

---

## Opening Sequences

Guided Renumber maintains four independent numbering sequences:

| Sequence | Openings |
| --- | --- |
| `W##` | New windows and curtain walls |
| `Wx##` | Existing windows and curtain walls |
| `D##` | New doors |
| `Dx##` | Existing doors |

Curtain walls share the Window sequence.

Demolished openings are not included in the Guided Renumber workflow.

---

## Start Guided Renumber

Run **Guided Renumber** from Openings Manager or the corresponding Flow command.

The start dialog allows you to review the starting number for each sequence:

- New Windows
- Existing Windows
- New Doors
- Existing Doors

The Window sequences also apply to curtain walls.

---

## Choose the Starting Numbers

Flow can initialise the sequences from the project or from the previous Guided Renumber session.

Depending on the available information, you can:

- continue from the previous session
- continue from the highest existing project marks
- enter the starting numbers manually
- reset the sequences to `01`

Review the starting values before beginning the selection workflow.

!!! tip "Check the starting values"

    If you are continuing a partially numbered project, confirm the W, Wx, D and Dx starting values before starting the selection sequence.

---

## Work Through the Project by Level

Guided Renumber processes project levels from the lowest elevation upwards.

Flow activates an appropriate working floor plan for the current level where one is available.

The Guided Renumber palette shows:

- the current level
- progress through the project levels
- the active numbering workflow

---

## Select Openings in Numbering Order

Select the openings directly from the Revit model in the order in which they should be numbered.

For example:

```text
First selected New window  → W01
Second selected New window → W02
Selected New curtain wall  → W03
Third selected New window  → W04
```

Doors maintain their own sequence:

```text
First selected New door  → D01
Second selected New door → D02
```

Existing openings similarly use the Wx and Dx sequences.

The order in which you select the openings determines the proposed numbering order.

---

## Selecting the Wrong Opening

Guided Renumber includes checks to protect the active sequence.

Flow prevents or ignores selections that cannot be used in the current workflow, including:

- an opening from another level
- an opening already selected in the current sequence
- a demolished opening

This helps keep the numbering session aligned with the current level.

---

## Undo Last

Use **Undo Last** to remove the most recently selected opening from the current Guided Renumber sequence.

Flow then recalculates the proposed marks for the remaining selected openings.

For example, if you selected:

```text
W01
W02
W03
```

and undo the last selection, the current sequence returns to:

```text
W01
W02
```

You can then continue selecting.

---

## Finish the Current Level

When you have completed the openings on the current level, click:

**Finish Level**

Flow advances the Guided Renumber workflow to the next available level.

Continue until the required project levels have been reviewed.

---

## Apply Numbering

When the required openings have been selected, click:

**Apply Numbering**

Flow applies the proposed marks to the selected openings.

If some project openings have not been included, Flow identifies the incomplete levels and asks whether you want to apply numbering only to the openings selected so far.

This allows a partial numbering session to be committed deliberately.

!!! warning "Finish Session is not Apply Numbering"

    **Finish Session** exits the Guided Renumber session without applying the proposed numbering.

    Use **Apply Numbering** when you want the selected sequence written back to the Revit model.

---

## Existing Mark Conflicts

If a proposed mark is already being used by another opening in the same numbering group, Flow resolves the conflict before assigning the requested mark.

The conflicting opening is moved to the next available mark in that sequence.

This avoids deliberately leaving duplicate marks in the project while the new sequence is applied.

---

## Continue a Later Session

After a successful Guided Renumber operation, Flow remembers the next available values for:

```text
W
Wx
D
Dx
```

These values can be offered when the next Guided Renumber session begins.

This makes it possible to number a project progressively without manually remembering the last number used in each sequence.

---

## Guided Renumber and Curtain Walls

Curtain walls are numbered as part of the Window sequence.

They do not have a separate counter.

For example:

```text
W01  Window
W02  Curtain Wall
W03  Window
```

Existing curtain walls similarly use the `Wx##` sequence.

---

## Guided Renumber and Demolished Openings

Demolished openings are excluded from Guided Renumber.

The workflow is designed around openings that can be selected in the active working views used during the numbering session.

---

## After Renumbering

After applying the numbering:

1. Return to Openings Manager.
2. Refresh the register if required.
3. Review the updated marks.
4. Check for remaining non-standard or duplicate-mark issues.
5. Continue with opening documentation.

If opening views already exist, use **Standardise** or **Conform Views** where required to ensure the view names remain aligned with the revised opening information.

---

## Related Help

- [**Opening Marks**](opening-marks.md)
- [**Standardising Openings**](standardising-openings.md)
- [**Reviewing Openings**](reviewing-openings.md)
- [**Opening Views**](opening-views.md)