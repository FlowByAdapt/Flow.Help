# Gutter Caps

**Gutter Caps** creates a small solid cap at a selected end of a Revit
gutter.

The workflow is intended for closing open gutter ends quickly while
matching the shape of the gutter profile, without requiring a separate
end-cap family for every gutter type.

---

## Opening the Tool

Open:

**Flow → \[VERIFY PANEL NAME\] → Roof Tools → Gutter Caps**

---

## Before You Start

The command operates on a Revit **Gutter** element.

You can either select one gutter before starting the command or select
the gutter when prompted.

---

## Adding Gutter Caps

1. Open **Flow → \[VERIFY PANEL NAME\] → Roof Tools**.
2. Choose **Gutter Caps**.
3. Select the Revit gutter if one was not already selected.
4. Click near the gutter end that you want to cap.
5. Continue clicking near other ends of the same gutter as required.
6. Press **Esc** when you have finished placing caps.
7. Review the created caps.

The picked point identifies which end of the gutter should be capped.
You do not need to pick the end face precisely; pick close to the
required gutter end.

!!! info "What Flow does automatically"

    Flow identifies the gutter end nearest the picked point and builds the cap from the end profile.

    The cap extends a short distance beyond the gutter end with a small overlap to avoid a visible seam.

---

## Gutter Profile

The cap is generated from the geometry of the selected gutter end.

The established workflow rebuilds the outside envelope of the end
profile and closes the open gutter mouth with an orthogonal corner where
required. This is intended to avoid an unwanted diagonal closure across
an open gutter profile.

---

## Existing Caps

Before creating a cap, the established workflow checks for an existing
generated Gutter Cap near the selected end.

If a cap already exists at that location, the duplicate is skipped
rather than creating another cap in the same place.

!!! tip "Re-running the tool"

    This duplicate check makes it possible to return to a gutter and add a missing cap without intentionally stacking another generated cap over an existing one.

---

## What Flow Creates

The established workflow creates the gutter cap as a small solid
**DirectShape** element.

Where available, the gutter category material is applied to the
generated cap so that its appearance follows the gutter more closely.

The generated cap is a separate element. The original Revit gutter is
not reshaped or shortened by the operation.

!!! note "Generated geometry"

    Because the cap is generated geometry rather than part of the original Revit gutter, review it if the gutter type or profile is subsequently changed.

---

## Finishing the Workflow

Press **Esc** when you have finished selecting gutter ends.

The established workflow then selects the newly created caps and brings
them into view, making it easier to review the result.

---

## Checking the Result

After placing caps, check that:

- each intended gutter end is closed;
- the cap follows the expected gutter profile;
- the cap projects in the correct direction from the gutter end;
- the material appearance is appropriate; and
- no cap has been placed at an unintended end.

---

## Related Help

- [Roof Tools](index.md)
- [Roof Outline](roof-outline.md)
- [Roof Tools Troubleshooting](troubleshooting.md)