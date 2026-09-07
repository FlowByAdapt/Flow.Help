# Openings Manager Troubleshooting

Use these checks when Openings Manager or one of its associated workflows does not behave as expected.

Start with the section that most closely matches the command you were using.

---

## The Register Does Not Show Recent Changes

The Opening Register shows the results of its most recent discovery and audit.

If openings have been changed directly in Revit while Openings Manager remains open, the register can still show the previous state.

Click **Refresh** to rebuild the register.

!!! warning "Refresh modifies the model"

    Refresh is not read-only.

    Before rerunning discovery, Flow applies the Window `Sill Height` → `Zero Window Sill Height` Global Parameter rule.

Use Refresh deliberately, particularly in a project whose Window Global Parameter setup is still being reviewed.

➡️ [**Opening Global Parameters**](opening-global-parameters.md)

---

## An Opening Is Missing from the Register

Openings Manager discovers:

- Window instances
- Door instances
- Revit Curtain Walls

If an expected opening is missing:

1. confirm it is one of those supported element types
2. click **Refresh**
3. confirm the element exists in the current Revit document
4. for a Curtain Wall, confirm it is actually a Revit Wall whose Wall Type is a Curtain type

Unrelated model geometry is not treated as an opening merely because it visually resembles one.

---

## I Cannot Find an Opening in a Large Project

Use Search and the register filters to narrow the list.

Available filters include:

- Category
- Level
- Phase
- Tag Type
- GP Status

You can also:

- click a row to select its Revit element
- double-click a row to focus/zoom to the opening
- use **Focus** for the selected or first checked opening
- use **Select from Model** to pick an opening in Revit and locate its register row

➡️ [**Selecting and Locating Openings**](selecting-and-locating-openings.md)

---

## Select from Model Does Not Start Where I Expected

**Select from Model** requires the exact working 3D view:

```text
3D-01-Work Main
```

Flow switches to that view before model picking.

It does not automatically return to the view that was active before the selection operation.

If the workflow cannot activate the required view, check that the project contains the correctly named 3D view.

---

## My Checked Rows Disappeared

Changing certain register filters clears the checked-row selection.

This includes changes to filters such as:

- Category
- Level
- Phase
- GP Status

Set the required filters first, then check the openings or use **Select Filtered**.

Remember that a highlighted row and a checked row have different purposes:

- the highlighted row represents the current Revit/register selection
- checkboxes define working selections for commands that support checked scope

---

## An Opening Shows as Non-standard Even Though Its Mark Looks Correct

The register audit includes more than mark-format validation.

An opening can be reported as non-standard when its associated opening-view naming is inconsistent with the current opening information.

If the mark itself is correct, check whether an existing opening elevation needs to be renamed or conformed.

➡️ [**Standardising Openings**](standardising-openings.md)

➡️ [**Conforming Opening Views**](conforming-opening-views.md)

---

## Standardise Does Not Change an Opening

Standardise preserves marks that are already valid and unique.

It only assigns a new mark where the existing mark is invalid or conflicts within its numbering group.

Also check that the opening is included in the scope you selected:

- Checked
- Filtered
- All

Windows and Curtain Walls share the W/Wx numbering group. Doors use D/Dx.

➡️ [**Standardising Openings**](standardising-openings.md)

---

## Generate Views Says Openings Need Standardising

**Generate Views** validates the chosen register scope before creating Window or Door elevations.

If non-standard openings are found, Flow offers:

- **Standardise Now**
- **Cancel**

Choosing **Standardise Now** runs Standardise and then ends that Generate Views invocation.

!!! important "Generate Views does not resume automatically"

    After Standardise completes, click **Generate Views** again to start the generation workflow with the updated openings.

➡️ [**Generating Opening Views**](generating-opening-views.md)

---

## Renumber Will Not Accept an Opening

The interactive **Renumber** workflow validates each model pick.

A picked opening can be rejected when:

- it is on a different level from the current Renumber level
- it is Demolished
- it is not a Window, Door or Curtain Wall accepted by the workflow

Check the current level in the Renumber workflow before picking the opening.

➡️ [**Guided Renumbering**](guided-renumbering.md)

---

## I Cancelled Renumber and the Marks Did Not Change

This is expected if the proposed sequence had not been applied.

Model picking creates a temporary proposed numbering sequence.

Use **Apply** to write that sequence to the model.

Pressing **Esc** cancels the interactive session without applying the pending marks.

---

## A Plan Tag Is Not Created

Dashboard **Tag** requires the active Revit view to be a **Floor Plan**.

Check that:

- the active view is a Floor Plan
- the opening is visible in that view
- the chosen scope contains only one opening category
- a valid **Tag Type** is selected
- the selected tag type belongs to the correct Revit tag category

Flow skips an opening that is already tagged in the active view.

If Revit cannot tag one individual opening, the workflow can skip that element and continue with the others.

➡️ [**Tagging Openings**](tagging-openings.md)

---

## Tag Says the Scope Contains Mixed Categories

Dashboard tagging processes one opening category at a time.

A scope containing, for example, both Windows and Doors is rejected.

Set the Category filter first, then check the required openings or use **Select Filtered**.

Changing the Category filter clears the current checked selection.

---

## A Window View Is Not Generated

The standard **Generate Views** Window workflow creates elevations for **New Windows** in the chosen register scope.

Check that:

- the Window is New
- its opening information is standard
- it is included in the selected scope
- the required project view/tag resources are available

Existing and Demolished Windows are not generated by this workflow.

If the opening is a Curtain Wall, use **Curtain Wall Views** instead.

➡️ [**Generating Opening Views**](generating-opening-views.md)

---

## I Chose Standardise Now but No Views Were Created

This is expected behaviour.

When Generate Views detects non-standard openings, **Standardise Now** performs the standardisation and ends the current generation request.

Run **Generate Views** again after the register has been corrected.

---

## I Expected Several Door Views but Only One Was Created

Door elevations are **type-based**.

Multiple New Door instances using the same documented Door type can therefore correspond to one Door elevation.

Door view names are based on the Door type's **Type Mark** followed by:

```text
-D
```

➡️ [**Generating Opening Views**](generating-opening-views.md)

---

## A Curtain Wall Cannot Be Selected for View Generation

The **Curtain Wall Views** workflow requires the selected element to:

- be a Revit Curtain Wall
- use a Curtain Wall type whose name begins with `CW_`
- be in the New Construction phase

The Curtain Wall workflow is interactive and does not use the checked rows in the Opening Register.

---

## I Cancelled a Curtain Wall View but Its Mark Changed

This can occur because the Curtain Wall mark is standardised **before** Flow asks you to pick the elevation marker side.

If you cancel at the marker-side step, the mark change may already have been committed even though no elevation was created.

This differs from Renumber, where the proposed marks are not written until Apply.

➡️ [**Generating Opening Views**](generating-opening-views.md)

---

## Curtain Wall Views Is Asking Me to Choose a Plan

During the interactive Curtain Wall workflow, cancelling or being unable to continue the current pick can open a chooser containing suitable Floor Plans whose names end in:

```text
_Win
```

Choose the required plan to activate it and continue, or choose the finish option to end the workflow.

At startup, Flow first attempts to use the exact plan:

```text
X-01-GF_Win
```

---

## An Existing Opening View Is Incorrect

If the elevation already exists, try **Conform Views** before recreating it.

Depending on the resolved opening, Conform Views can restore or update:

- view template
- scale
- crop
- level datum extents
- phase and phase filter
- view name
- missing opening tag
- Window size metadata
- Curtain Wall metadata

➡️ [**Conforming Opening Views**](conforming-opening-views.md)

---

## Conform Views Skips a View

Flow does not modify a view solely because its name resembles an opening view.

It must be able to resolve the view to a suitable opening.

A view can therefore be skipped when:

- no suitable opening is visible
- the opening cannot be resolved reliably
- the view is ambiguous
- required project resources are unavailable

For **All Opening Views**, Flow scans recognised non-template section-view candidates and then validates them before applying opening-specific changes.

---

## A Window View Is Skipped During Dimensioning

Batch Window dimensioning scans views using the strict New Window naming pattern:

```text
W##
```

Curtain Wall elevations can also have W## names because Curtain Walls share the Window numbering sequence.

Flow then checks for a genuine Revit Window family instance.

If none is found, the view is skipped and can be reported as likely being a Curtain Wall elevation.

This is expected.

➡️ [**Dimensioning Window Views**](dimensioning-window-views.md)

---

## An Existing Window View Is Not Included in All Window Views

The batch dimensioning scan uses the New Window:

```text
W##
```

pattern.

Existing Window views using:

```text
Wx##
```

are not included in **All Window Views**.

---

## Window Dimensions Cannot Be Created

Window dimensioning depends on Flow being able to resolve suitable Revit geometry references from the component Window family.

If the required references cannot be found, Flow cannot reliably build the standard dimension set.

Check that:

- the elevation contains a component Revit Window
- the Window can be resolved by the dimensioning workflow
- the family exposes suitable dimension references

!!! warning "Existing dimensions are regenerated"

    On a successfully processed Window elevation, the existing dimensions are removed and the standard Flow dimensions are created again.

    Review manually customised dimensions before running the command.

---

## Window Placement Cannot Start

Window placement requires the sheet:

```text
A401
```

Check that:

- A401 exists
- eligible unplaced `W##` views exist
- the views are not already placed
- the selected placement area is large enough

New Curtain Wall elevations can participate when they use the eligible W## naming sequence.

➡️ [**Placing Views on Sheets**](placing-views-on-sheets.md)

---

## Window Placement Offers Resume or Reset

Flow stores placement state for the managed Window placement workflow.

If an earlier session exists, you can resume it or reset the recorded placement and start again.

Use Resume when the previous placements should be retained and the remaining views still need to be placed.

Use Reset when the managed placement layout should be discarded and rebuilt.

---

## I Stopped Window Placement Before Finishing

Choose **Stop and Resume Later** to retain the completed placement state.

Run **Place on Sheet → Window Views** again later and resume the stored session.

Flow can also remember the previous placement area so it can be reused on subsequent sheets.

---

## What Does Reset Window Placement Remove?

Reset uses the stored placement information to remove the viewports created by that managed placement session.

It does **not** delete:

- the underlying opening elevation views
- the sheets themselves

It then clears the placement memory so the managed workflow can start again.

---

## Door Placement Cannot Start

Door placement requires a sheet named exactly:

```text
Interior Opening Schedule
```

Check that:

- the sheet exists
- eligible unplaced `-D` views exist
- the selected placement area is large enough

Unlike Window placement, Door placement does not automatically create additional schedule sheets or use the same persisted Resume / Reset system.

---

## Door Heights Changed More Doors Than I Checked

The current **Door Heights** button in Openings Manager does not use the checked register rows as its scope.

It launches the project Door Height workflow and evaluates project Doors by level.

Checking individual Door rows before clicking Door Heights therefore does not restrict the dashboard operation to those Doors.

➡️ [**Door Heights**](door-heights.md)

---

## A Door Height Was Not Updated

Door Height adjustment is applied to applicable **New Doors**.

Check that:

- the Door is New
- its type provides a usable `Panel Width`
- the Door's level has a target height
- a newly created target type can use a writable `Panel Height`
- the required target type can be found or created within the same Door family
- the Door does not already use the required target type

Existing and Demolished Doors are skipped when changes are applied.

---

## A Door Height Type Cannot Be Created

Flow creates or reuses Door types using:

```text
<width>w x <height>h
```

For example:

```text
810w x 2200h
```

The type is reused only within the same Door family.

If it does not already exist, Flow duplicates the current type and attempts to set its `Panel Height`.

If Revit cannot complete that type creation successfully, the type-creation transaction is rolled back.

---

## GP Status Shows Override

A Window can display:

```text
Override
```

in the GP status information.

However, the current **GP Status** filter does not contain a separate Override choice.

Use **All** or the other register filters to locate and review the Window.

For head-height-specific information, also review the **Head Height GP** column.

➡️ [**Opening Global Parameters**](opening-global-parameters.md)

---

## Refresh Changed Window Parameter Associations

This can be expected.

Before rebuilding the register, Refresh applies the standard Window:

```text
Sill Height
    ↓
Zero Window Sill Height
```

Global Parameter rule.

Initial opening of Openings Manager performs discovery/audit, whereas the explicit Refresh command also applies this rule.

---

## A Window Head Height Override Cannot Be Removed

The documented individual override-removal workflow recognises Flow override associations following:

```text
Window Head Height_...
```

An unrelated Global Parameter is not automatically treated as a removable individual Flow override.

For wider association review, use **Parameters Manager**.

➡️ [**Window Head Height Overrides**](head-height-overrides.md)

---

## The Problem Is Still Not Resolved

If the issue remains:

1. identify the exact opening, view, sheet or parameter involved
2. confirm its Category, Level and Phase
3. determine whether the problem affects one item or a complete workflow
4. review any completion/result message from the command
5. check the prerequisites on the relevant help page
6. use Parameters Manager where the issue concerns wider Global Parameter associations

Avoid repeatedly running a modifying command when Revit is consistently reporting the same failure. Identify the affected resource or model condition first.

---

## Related Help

- [**Reviewing Openings**](reviewing-openings.md)
- [**Selecting and Locating Openings**](selecting-and-locating-openings.md)
- [**Opening Marks**](opening-marks.md)
- [**Standardising Openings**](standardising-openings.md)
- [**Guided Renumbering**](guided-renumbering.md)
- [**Tagging Openings**](tagging-openings.md)
- [**Generating Opening Views**](generating-opening-views.md)
- [**Conforming Opening Views**](conforming-opening-views.md)
- [**Dimensioning Window Views**](dimensioning-window-views.md)
- [**Placing Views on Sheets**](placing-views-on-sheets.md)
- [**Door Heights**](door-heights.md)
- [**Opening Global Parameters**](opening-global-parameters.md)
- [**Window Head Height Overrides**](head-height-overrides.md)
