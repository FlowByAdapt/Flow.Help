# Tagging Openings

Use **Tag Openings** to add the appropriate Revit tag to selected
windows, doors or curtain walls.

Tagging is designed to work from a floor plan and uses the tag type
selected in Openings Manager.

------------------------------------------------------------------------

## Before You Start

Open a **Floor Plan** containing the openings you want to tag.

Use the Openings Manager register to select or filter the required
openings.

!!! info "Floor plans only"

    The tagging workflow operates from a Floor Plan.

    If the active view is not a Floor Plan, switch to an appropriate plan before running the command.

------------------------------------------------------------------------

## Choose the Tag Type

The available tag types in Openings Manager change according to the
selected opening category.

Flow supports category-appropriate tag types for:

-   Windows
-   Doors
-   Curtain Walls

Select the required tag type before running the tagging command.

------------------------------------------------------------------------

## Tag Selected Openings

1.  Open the required Floor Plan.
2.  Select the openings you want to tag.
3.  Confirm that the required tag type is selected.
4.  Run **Tag Openings**.
5.  Review the result in the active view.

Flow creates the appropriate Revit tag and applies the selected tag
type.

------------------------------------------------------------------------

## Existing Tags

Flow checks whether an opening is already tagged in the active view.

If an appropriate tag already exists, Flow does not create a duplicate
tag for that opening.

------------------------------------------------------------------------

## Mixed Categories

Windows, doors and curtain walls use different Revit tag categories.

A mixed-category selection cannot be tagged as a single operation.

If your current selection contains more than one opening category:

1.  Filter or select one category.
2.  Run the tagging command.
3.  Repeat for the next category as required.

!!! tip "Filter before tagging"

    For larger projects, use the **Category** filter in Openings Manager before selecting the openings to tag.

------------------------------------------------------------------------

## If an Opening Cannot Be Tagged

Some elements may not be taggable in the current view.

If Revit cannot create a tag for an individual opening, Flow skips that
opening rather than stopping the entire tagging operation.

Check that:

-   the opening is visible in the active Floor Plan
-   the correct opening category is selected
-   the selected tag type is appropriate for that category

------------------------------------------------------------------------

## Related Help

-   [**Reviewing Openings**](reviewing-openings.md)
-   [**Selecting and Locating Openings**](selecting-and-locating-openings.md)
-   [**Opening Views**](opening-views.md)
-   [**Openings Manager Troubleshooting**](troubleshooting.md)