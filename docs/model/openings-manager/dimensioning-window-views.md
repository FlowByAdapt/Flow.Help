# Dimensioning Window Views

Use **Dimension Window Views** to create or regenerate the standard dimensions on component Window elevations.

The command can process the active Window view or batch-process recognised New Window views.

Curtain Wall elevations are not dimensioned by this workflow.

---

## Choose the Scope

From Openings Manager, click **Dimension Window Views**.

Choose:

- **Active Window View**
- **All Window Views**

Use **Active Window View** when working on one Window elevation.

Use **All Window Views** to process the recognised Window elevations throughout the project.

!!! note "Register checkboxes are not used"

    Dimension Window Views does not use the Checked / Filtered / All scope from the Opening Register.

    Its scope is based on the active view or the recognised Window elevation views.

<!-- SCREENSHOT: Dimension Window Views chooser showing Active Window View and All Window Views. -->

---

## All Window Views

For the batch operation, Flow looks for Revit section views whose names match the standard New Window convention:

```text
W##
```

For example:

```text
W01
W02
W03
```

Existing Window views using:

```text
Wx##
```

are not included in the batch scan.

This means **All Window Views** is specifically aimed at the standard New component Window elevation set.

---

## Active Window View

Use **Active Window View** when you only want to regenerate the dimensions on the elevation currently open in Revit.

Flow attempts to resolve a Window family instance from that view before dimensioning it.

If no suitable Window can be found, the view is not dimensioned.

---

## Curtain Wall Views

New Curtain Wall elevations can also use W## names because Curtain Walls share the Window opening-mark sequence.

They can therefore be encountered during the **All Window Views** scan.

Flow then checks the view for a genuine Revit Window family instance.

If no Window instance can be resolved, the view is skipped.

A batch result can identify this as:

```text
No window found (likely curtain wall view)
```

!!! info "Curtain Walls are intentionally skipped"

    Dimension Window Views is designed for component Window families.

    A W## Curtain Wall elevation appearing in the batch scan is an expected candidate, but it is not dimensioned by this command.

---

## How Flow Finds Dimension References

The dimensioning workflow resolves Revit references from the Window family geometry.

It looks for the references required to establish the standard Window dimension strings rather than placing dimensions from arbitrary points in the elevation.

The exact result therefore depends on the Window family exposing suitable references that Flow can resolve.

If the required references cannot be found, Flow cannot reliably create the standard dimension set for that view.

---

## Standard Dimensions

For a successfully resolved component Window elevation, Flow creates the standard Window documentation dimensions supported by the available references.

These include the opening's principal horizontal and vertical dimensions and the level-related dimensioning required by the Flow Window elevation standard.

<!-- SCREENSHOT: Completed W## component Window elevation showing the standard regenerated dimension set. -->

---

## Existing Dimensions Are Regenerated

Dimension Window Views is a **regeneration** workflow, not an append workflow.

For a Window elevation that is successfully processed, the existing dimensions in that view are removed and the Flow standard dimensions are created again.

!!! warning "Review manually customised dimensions first"

    Existing dimensions in a successfully processed Window elevation are replaced.

    If a view contains manually customised dimensioning that must be retained, review it before running Dimension Window Views.

This behaviour is useful when the Window geometry or documentation setup has changed and the complete standard dimension set needs to be rebuilt.

---

## If Dimensioning Cannot Be Completed

Flow does not deliberately leave a successfully processed view with a random partial set of new dimensions.

If the required Window or dimension references cannot be resolved, the view can be skipped or reported as failed depending on where the operation could not continue.

Typical causes include:

- the view is actually a Curtain Wall elevation
- no component Window can be resolved in the view
- the Window family does not expose the references needed by the dimensioning workflow
- the view does not meet the expected Window elevation conditions

---

## Batch Results

When **All Window Views** is used, Flow summarises the batch outcome.

The result distinguishes successfully dimensioned views from views that were skipped or failed.

This is useful because a W## batch can legitimately contain Curtain Wall views that should be skipped rather than treated as dimensioning failures.

Review the result before moving on to sheet placement.

---

## Recommended Workflow

For a new Window documentation set:

1. Resolve the opening marks.
2. Generate the Window elevations.
3. Conform existing elevations where required.
4. Run **Dimension Window Views**.
5. Review the regenerated dimensions.
6. Place the opening views on sheets.

➡️ [**Generating Opening Views**](generating-opening-views.md)

➡️ [**Conforming Opening Views**](conforming-opening-views.md)

➡️ [**Placing Views on Sheets**](placing-views-on-sheets.md)

---

## If a Window View Is Skipped

Check that:

- the view represents a component Revit Window rather than a Curtain Wall
- a suitable Window family instance can be resolved in the elevation
- the Window family exposes the references required by the dimensioning workflow
- for **All Window Views**, the view uses the expected `W##` naming convention

If the view already exists but its broader setup is incorrect, run **Conform Views** before retrying dimensioning.

➡️ [**Openings Manager Troubleshooting**](troubleshooting.md)

---

## Related Help

- [**Generating Opening Views**](generating-opening-views.md)
- [**Conforming Opening Views**](conforming-opening-views.md)
- [**Placing Views on Sheets**](placing-views-on-sheets.md)
- [**Openings Manager Troubleshooting**](troubleshooting.md)
