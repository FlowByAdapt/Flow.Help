# Openings Manager Troubleshooting

Use the following checks if Openings Manager or one of its associated
workflows is not behaving as expected.

------------------------------------------------------------------------

## The Register Does Not Show Recent Changes

Openings Manager displays the results of its most recent opening
discovery and audit.

If openings have been changed directly in Revit while the Manager
remains open, the register may still show the previous state.

Use **Refresh** to run the audit again.

Refresh is particularly useful after:

-   changing opening marks
-   changing opening types
-   creating or conforming opening views
-   changing Global Parameter associations
-   modifying opening parameters directly in Revit

------------------------------------------------------------------------

## An Opening Is Missing from the Register

Check that the element is a supported opening category:

-   Window
-   Door
-   Curtain Wall

Then refresh the register.

If the opening is still missing, confirm that the element is a valid
Revit opening element rather than unrelated model geometry.

------------------------------------------------------------------------

## I Cannot Find an Opening in a Large Project

Use the register filters and search before trying to locate the opening
manually.

You can narrow the register by information such as:

-   category
-   level
-   phase
-   Global Parameter status
-   opening mark or other searchable information

You can also double-click an opening row to locate the corresponding
element in Revit.

➡️ [**Selecting and Locating
Openings**](selecting-and-locating-openings.md)

------------------------------------------------------------------------

## Standardise Does Not Change an Opening

The opening may already use the expected Flow mark.

If all selected openings are already standard, Flow reports that no mark
changes were required.

Also check that the opening is included in the selected Standardise
scope.

➡️ [**Standardising Openings**](standardising-openings.md)

------------------------------------------------------------------------

## Generate Views Says Openings Need Standardising

Generate Opening Views checks the selected openings before creating
documentation.

If non-standard openings are found, Flow stops the generation workflow
and offers:

-   **Standardise Now**
-   **Cancel**

Choose **Standardise Now** to correct the marks before continuing.

➡️ [**Generating Opening Views**](generating-opening-views.md)

------------------------------------------------------------------------

## Guided Renumber Will Not Accept an Opening

Guided Renumber protects the active numbering workflow.

A selection may be rejected or ignored if:

-   the opening belongs to another level
-   the opening has already been selected in the current sequence
-   the opening is Demolished

Guided Renumber processes the project level by level.

Check the current level shown in the Guided Renumber palette before
selecting the opening.

➡️ [**Guided Renumbering**](guided-renumbering.md)

------------------------------------------------------------------------

## I Finished Guided Renumber but the Marks Did Not Change

**Finish Session** and **Apply Numbering** perform different actions.

**Finish Session** exits the Guided Renumber session without applying
the proposed numbering.

Use:

**Apply Numbering**

when you want the selected sequence written back to the Revit model.

------------------------------------------------------------------------

## A Tag Is Not Created

Opening tagging operates from a **Floor Plan**.

Check that:

-   the active view is a Floor Plan
-   the opening is visible in the active view
-   the correct opening category is being processed
-   an appropriate tag type is selected

Flow does not create a duplicate tag where an appropriate tag already
exists in the active view.

If Revit cannot tag an individual opening, Flow can skip that element
rather than stopping the complete tagging run.

➡️ [**Tagging Openings**](tagging-openings.md)

------------------------------------------------------------------------

## A Window View Is Not Generated

The standard Window view-generation workflow is intended for **New
windows**.

Check that:

-   the Window is New
-   the Window has a standard mark
-   the Window is included in the selected scope

If the opening is a curtain wall, use the dedicated Curtain Wall view
workflow instead.

➡️ [**Generating Opening Views**](generating-opening-views.md)

------------------------------------------------------------------------

## I Expected Several Door Views but Only One Was Created

Door documentation is **type-based**.

Flow creates one elevation for each applicable New door type, rather
than one view for every door instance.

Multiple doors using the same type therefore share the same Door
documentation view.

➡️ [**Generating Opening Views**](generating-opening-views.md)

------------------------------------------------------------------------

## A Curtain Wall View Is Not Generated

Check that:

-   the selected element is a valid curtain wall for the configured
    workflow
-   the curtain wall is New
-   it uses the expected opening marking standard
-   a view with the required name does not already exist

The Curtain Wall workflow also requires you to select the side on which
the elevation marker should be placed.

➡️ [**Generating Opening Views**](generating-opening-views.md)

------------------------------------------------------------------------

## An Existing Opening View Is Incorrect

If an opening elevation already exists but its setup is no longer
correct, use **Conform Views** before recreating it.

Conform Views can restore or update items including:

-   view template
-   scale
-   crop region
-   phase settings
-   view name
-   opening tag
-   opening metadata

➡️ [**Conforming Opening Views**](conforming-opening-views.md)

------------------------------------------------------------------------

## Conform Views Skips a View

Flow only modifies views that it can recognise and resolve as opening
elevations.

A view can be skipped if Flow cannot determine the opening associated
with it.

Check the view naming and the associated opening information before
trying again.

------------------------------------------------------------------------

## A Window View Is Skipped During Dimensioning

Batch Window dimensioning processes recognised `W##` views.

Curtain wall elevations also use W-style names, so they can be
encountered during the batch scan.

If Flow cannot find a genuine Revit Window family instance in the view,
it can report:

``` text
No window found (likely curtain wall view)
```

This is an expected skip for a curtain wall elevation.

➡️ [**Dimensioning Window Views**](dimensioning-window-views.md)

------------------------------------------------------------------------

## Window Dimensions Cannot Be Created

The complete Window dimensioning workflow expects named references in
the Window family:

-   Left
-   Right
-   Sill
-   Head
-   FFL

If the required Left/Right or Sill/Head references are unavailable, Flow
cannot create the standard dimension set.

If FFL is unavailable, Width and Height may still be created.

!!! warning "Existing dimensions are regenerated"

    The dimensioning workflow removes the existing dimensions in a processed Window elevation before creating the standard Flow dimensions.

    Review manually customised dimensions before running the command.

------------------------------------------------------------------------

## Window View Placement Cannot Start

The Window placement workflow requires sheet:

``` text
A401
```

Check that:

-   A401 exists
-   the required `W##` views exist
-   the views are not already placed
-   the selected placement area is large enough

➡️ [**Placing Opening Views on Sheets**](placing-views-on-sheets.md)

------------------------------------------------------------------------

## I Stopped Window Placement Before Finishing

Window placement supports a persisted placement session.

If you choose **Stop and Resume Later**, Flow records the placement
progress so the remaining views can be continued later.

Run the placement workflow again to continue.

------------------------------------------------------------------------

## I Need to Undo the Previous Window Placement Session

Where a recorded Window placement session exists, use:

**Reset Previous Session**

Flow removes the viewports recorded by that placement session and clears
the placement memory.

It does **not** delete the elevation views or the sheets.

------------------------------------------------------------------------

## Door View Placement Cannot Start

Door placement looks for a sheet named exactly:

``` text
Interior Opening Schedule
```

Check that:

-   the sheet exists
-   the required `-D` Door views exist
-   the views are not already placed
-   the selected placement area is large enough

Unlike Window placement, the Door workflow does not automatically create
additional schedule sheets.

------------------------------------------------------------------------

## Door Heights Reports Updates but a Door Did Not Change

Check that:

-   the door is New
-   the door family provides a usable **Panel Width**
-   the door type provides a usable **Panel Height**
-   a target height exists for the door's level
-   the door is included where a selected-door workflow is being used

Existing and Demolished doors are deliberately skipped.

➡️ [**Door Heights**](door-heights.md)

------------------------------------------------------------------------

## A Door Height Type Cannot Be Created

Flow creates or reuses Door types using the naming format:

``` text
<width>w x <height>h
```

For example:

``` text
810w x 2200h
```

The Door family needs usable **Panel Width** and **Panel Height**
parameters for this workflow.

Flow rolls back an unsuccessful type creation rather than deliberately
leaving a partially configured Door type.

------------------------------------------------------------------------

## A Global Parameter Status Is Missing or Incomplete

Openings Manager audits the expected opening Global Parameter
associations.

Check the relevant opening setup, including:

-   Window sill-height association
-   Window head-height association
-   Door display controls
-   Door trim controls
-   Architrave dimensions
-   Door opening settings

Use **Refresh** after changing the associations.

➡️ [**Opening Global Parameters**](opening-global-parameters.md)

------------------------------------------------------------------------

## An Architrave Global Parameter Has the Wrong Value

When Flow creates the standard Architrave Length Global Parameters, the
intended initial values are:

``` text
Architrave_Depth = 20 mm
Architrave_Width = 60 mm
```

If an existing project Global Parameter already has a different value,
review the existing project setup rather than assuming Flow will
overwrite it.

Flow reuses existing Global Parameters where they are already present.

------------------------------------------------------------------------

## A Window Head Height Override Cannot Be Removed

The individual override-removal workflow only treats recognised Flow
override names as removable overrides.

The expected pattern is:

``` text
Window Head Height_...
```

If the Window is associated with an unrelated Global Parameter, Flow
does not treat that association as a Flow head-height override.

➡️ [**Window Head Height Overrides**](head-height-overrides.md)

------------------------------------------------------------------------

## A Window Has No Standard Head Height Association

The head-height override workflows can repair a missing standard
association before creating or removing an override.

The normal standards are:

  Window     Global Parameter
  ---------- ------------------------
  New        `Window Head Height`
  Existing   `X-Window Head Height`

Refresh Openings Manager after repairing the association.

------------------------------------------------------------------------

## The Problem Is Still Not Resolved

If the issue remains:

1.  Refresh Openings Manager.
2.  Confirm the affected opening category, phase and level.
3.  Check whether the issue affects one opening or multiple openings.
4.  Review the completion summary from the command.
5.  Check the relevant workflow page for its prerequisites.
6.  If appropriate, review the project Global Parameter setup in
    Parameters Manager.

Avoid repeatedly running a modification command if Revit is reporting a
persistent error. Identify the affected opening, view or parameter
first.

------------------------------------------------------------------------

## Related Help

-   [**Reviewing Openings**](reviewing-openings.md)
-   [**Opening Marks**](opening-marks.md)
-   [**Guided Renumbering**](guided-renumbering.md)
-   [**Opening Views**](opening-views.md)
-   [**Door Heights**](door-heights.md)
-   [**Opening Global Parameters**](opening-global-parameters.md)
-   [**Window Head Height Overrides**](head-height-overrides.md)