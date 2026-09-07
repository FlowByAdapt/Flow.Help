# Conforming Opening Views

Use **Conform Views** to repair existing opening elevations and bring recognised views back into line with the current Flow opening standards.

This is useful when opening marks, view settings, tags or model information have changed after an elevation was created.

---

## What Conform Views Does

Conform Views is more than a crop-adjustment tool.

For a recognised opening view, Flow can update the parts of the view that it is able to resolve, including:

- view template
- view scale
- crop region
- level datum extents
- phase and phase filter
- view name
- missing opening tag
- Window size metadata
- Curtain Wall metadata

The exact work depends on the opening and what Flow can resolve for that view.

!!! info "Conform works with existing views"

    Use Conform Views when an opening elevation already exists but no longer matches the expected documentation setup.

    It is generally preferable to repair a recognised view rather than deliberately creating a duplicate elevation.

---

## Choose the Scope

Click **Conform Views** in Openings Manager.

Flow offers:

- **Active View**
- **All Opening Views**
- **Cancel**

This command does not use the checked rows in the Opening Register.

<!-- SCREENSHOT: Conform Views chooser showing Active View and All Opening Views. -->

---

## Active View

Use **Active View** when you want to repair the opening elevation currently active in Revit.

1. Open the required opening elevation.
2. Click **Conform Views**.
3. Choose **Active View**.
4. Allow Flow to resolve the opening represented by the view.
5. Review the result.

If the active view cannot be recognised and resolved as an opening view, Flow does not arbitrarily modify it.

---

## All Opening Views

Use **All Opening Views** when a collection of existing opening elevations needs to be checked.

The batch workflow scans non-template Revit section views whose names follow the recognised opening-view patterns, including W-style views and Door views ending in `-D`.

Each candidate is then passed through the conform process.

Views that cannot be resolved to an opening are skipped rather than being modified based only on their name.

!!! note "A candidate name is not enough"

    Flow attempts to identify the opening represented by the view before applying opening-specific changes.

    A view that merely looks like an opening view can therefore be skipped if the associated opening cannot be resolved reliably.

---

## Resolving the Opening

Flow uses the opening views and the model elements visible in them to associate an existing elevation with its opening.

Recognised opening views can represent:

- Windows
- Doors
- Curtain Walls

For opening lookup, Flow expects a view to resolve cleanly to a single visible top-level opening.

This protects unrelated or ambiguous views from being modified as though they were standard opening elevations.

---

## View Naming

Once the associated opening is resolved, Flow can bring the view name back into line with the current opening information.

For Windows and Curtain Walls, the W/Wx opening mark provides the basis for the elevation name.

Door elevations use the type-based Door documentation naming convention ending in:

```text
-D
```

This is particularly useful after opening marks or Door type information have changed.

➡️ [**Opening Marks**](opening-marks.md)

---

## View Template and Scale

Conform Views can reapply the expected view template and scale for the resolved opening type.

The current Window/Curtain Wall documentation standards include:

- section type `5.6_WINDOW ELEVATIONS`
- view template `bc_SEC_WDW-SCHED`
- scale 1:50

Door elevations use their corresponding configured Door elevation standards.

Use Conform when a view has been manually altered or no longer follows the expected opening documentation setup.

---

## Crop Region

Flow activates and conforms the crop for the resolved opening where the conform operation supports it.

This can repair elevations whose crop has been manually moved or resized and no longer frames the opening correctly.

The crop operation uses the current opening geometry and the configured opening-view padding/depth settings rather than simply restoring a previously saved crop rectangle.

<!-- SCREENSHOT: Opening elevation before/after Conform showing a corrected crop and standard view appearance. -->

---

## Level Datum Extents

Conform Views can clean up the level datum extents in the opening elevation.

This is part of bringing the documentation view back to the expected Flow presentation rather than only correcting the opening crop.

---

## Phase Settings

Where the required project phase resources can be resolved, Conform Views sets the standard opening documentation phase setup:

- **Phase:** New Construction
- **Phase Filter:** Show Previous + New

This keeps the recognised opening elevations consistent with the intended documentation state.

---

## Missing Elevation Tags

Conform Views checks for the expected opening tag and can add it when it is missing and the required tag resource is available.

The appropriate tag depends on whether the resolved opening is a:

- Window
- Door
- Curtain Wall

Existing appropriate tags are not deliberately duplicated simply because Conform is run again.

---

## Opening Metadata

Conforming can also update opening-related metadata used by the documentation workflow.

Depending on the resolved opening, this can include:

- **Window Size O/A** information for Windows
- Curtain Wall metadata for Curtain Walls

This helps an existing elevation remain aligned with the current model rather than only restoring its visual settings.

---

## What Conform Does Not Assume

Conform Views does not modify every section view whose name happens to resemble an opening.

A view can be skipped when Flow cannot reliably determine the opening it represents.

Possible reasons include:

- no suitable opening is visible in the view
- more than one top-level opening is visible
- the view cannot be associated with the expected opening workflow
- required Revit/project resources are unavailable

This is intentional protection against applying opening standards to an ambiguous view.

➡️ [**Openings Manager Troubleshooting**](troubleshooting.md)

---

## When to Use Conform Views

Use Conform Views when:

- an opening mark has changed
- an opening view name no longer matches the opening
- the view template or scale has been altered
- the crop no longer frames the opening correctly
- level datum extents need restoring
- the standard phase setup has changed
- an expected opening elevation tag is missing
- Window or Curtain Wall documentation metadata needs updating
- existing opening elevations need to be returned to the Flow standard

!!! tip "Repair before recreating"

    If the required opening elevation already exists, try **Conform Views** before creating another view.

---

## Conform Views vs Standardise

The two commands overlap in one important area but have different purposes.

**Standardise** primarily repairs opening marks and synchronises opening-view names.

**Conform Views** works on existing opening elevations and can restore a broader set of documentation properties such as the template, scale, crop, datum extents, phase settings, tags and metadata.

Use Standardise for opening-mark compliance. Use Conform Views for broader existing-view maintenance.

➡️ [**Standardising Openings**](standardising-openings.md)

---

## After Conforming

After the operation:

1. Review the affected opening elevations.
2. Check any views that were skipped or could not be resolved.
3. Dimension the standard Window views where required.
4. Place the opening views on sheets.
5. Review the Opening Register again as required.

Remember that **Refresh** also applies the Zero Window Sill Height rule before rebuilding the register.

➡️ [**Dimensioning Window Views**](dimensioning-window-views.md)

➡️ [**Placing Views on Sheets**](placing-views-on-sheets.md)

---

## Related Help

- [**Generating Opening Views**](generating-opening-views.md)
- [**Standardising Openings**](standardising-openings.md)
- [**Opening Marks**](opening-marks.md)
- [**Dimensioning Window Views**](dimensioning-window-views.md)
- [**Placing Views on Sheets**](placing-views-on-sheets.md)
- [**Openings Manager Troubleshooting**](troubleshooting.md)
