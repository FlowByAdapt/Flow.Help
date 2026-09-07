# Tagging Openings

Use **Tag** to add Revit tags to Windows, Doors or Curtain Walls from the Opening Register.

The dashboard tagging workflow uses the current register scope and the **Tag Type** selected in Openings Manager.

---

## Before You Start

Open the **Floor Plan** in which the tags should be created.

Tagging from Openings Manager only runs when the active Revit view is a Floor Plan.

!!! important "Floor Plans only"

    If the active view is not a Floor Plan, Flow stops the tagging workflow and asks you to switch to an appropriate plan.

The openings also need to be visible in the active plan for Revit to create useful tags there.

---

## Choose the Openings to Tag

From the Opening Register:

1. Set the required filters.
2. Check individual openings if required, or prepare a filtered group.
3. Make sure the intended scope contains only one opening category.
4. Select the required **Tag Type**.
5. Click **Tag**.
6. Choose the required scope when prompted.

Depending on the register state, the tagging scope can be based on:

- **Checked** openings
- **Filtered** openings
- **All** openings

➡️ [**Selecting and Locating Openings**](selecting-and-locating-openings.md)

<!-- SCREENSHOT: Openings Manager in front of a Floor Plan, filtered to one category, with several checked openings and the Tag Type control visible. -->

---

## Tag Type

The available **Tag Type** choices change with the opening category.

Flow uses the corresponding Revit tag category:

| Opening | Revit tag category |
| --- | --- |
| Window | Window Tags |
| Door | Door Tags |
| Curtain Wall | Wall Tags |

Choose the required tag type before running **Tag**.

When tagging is launched from the Openings Manager dashboard, the selected Tag Type is the type Flow uses for the operation.

!!! note

    If no valid Tag Type is selected, the dashboard tagging operation does not continue.

---

## Tag One Category at a Time

A tagging scope must contain exactly one opening category.

For example, a scope containing both Windows and Doors cannot be tagged in a single operation.

If the chosen scope contains mixed categories, Flow stops and asks you to select only one category.

For a mixed project:

1. Filter to **Windows** and tag the required Windows.
2. Filter to **Doors** and repeat.
3. Filter to **Curtain Walls** and repeat if required.

!!! tip "Category first, selection second"

    Changing the Category filter clears the checked selection.

    Set the category first, then check the required openings or use **Select Filtered**.

---

## What Flow Does

For each opening in the selected scope, Flow:

1. checks whether that element is already tagged in the active view
2. skips it if a tag already targets that opening
3. determines a tag point from the element location or bounding box
4. creates a horizontal Revit tag without a leader using the selected tag type

The operation is carried out in the active Floor Plan.

---

## Existing Tags

Flow checks the active view for tags already associated with the selected openings.

If an opening is already tagged in that view, Flow skips it rather than deliberately creating another tag for the same element.

!!! info "The check is view-specific"

    Tagging in one Floor Plan does not mean the opening is considered tagged in every other plan.

    The workflow checks the active view in which the tagging operation is being run.

---

## Tag Position

Tags are created at an automatically determined point.

For point-based opening elements, Flow uses the element's location point.

Where that is not available, Flow attempts to use the centre of the element's bounding box.

The tag is created:

- horizontally
- without a leader

You can reposition the resulting Revit tags afterwards using normal Revit editing if the documentation layout requires adjustment.

---

## If an Opening Cannot Be Tagged

Flow processes the openings individually.

If Revit cannot create a tag for a particular opening, that opening is skipped rather than causing every remaining opening in the scope to fail.

If an expected tag is missing, check:

- the active view is a **Floor Plan**
- the opening is visible in that view
- the tagging scope contains only one opening category
- a valid Tag Type is selected
- the selected Revit tag type is suitable for the opening category
- Revit can obtain a usable location or bounding box for the element

➡️ [**Openings Manager Troubleshooting**](troubleshooting.md)

---

## Dashboard Tagging and Automatic View Tags

The **Tag** command described on this page applies tags to openings in a Floor Plan.

This is separate from the tags that Flow can add automatically to generated or conformed opening elevations.

For example, opening-view generation can apply the configured schedule tag when the required project tag family is available.

➡️ [**Generating Opening Views**](generating-opening-views.md)

➡️ [**Conforming Opening Views**](conforming-opening-views.md)

---

## Recommended Workflow

For a larger project:

1. Open the required Floor Plan.
2. Set **Category** to the opening category you want to tag.
3. Apply Level, Phase or Search filters if required.
4. Check individual records or use **Select Filtered**.
5. Select the required **Tag Type**.
6. Click **Tag**.
7. Choose the required scope.
8. Review and reposition the resulting Revit tags where necessary.
9. Repeat for other opening categories or plans.

<!-- SCREENSHOT: Floor Plan after tagging, showing several newly created opening tags with a clean, readable result. -->

---

## Related Help

- [**Reviewing Openings**](reviewing-openings.md)
- [**Selecting and Locating Openings**](selecting-and-locating-openings.md)
- [**Generating Opening Views**](generating-opening-views.md)
- [**Conforming Opening Views**](conforming-opening-views.md)
- [**Openings Manager Troubleshooting**](troubleshooting.md)
