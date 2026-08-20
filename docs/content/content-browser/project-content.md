# Project Content

Content Browser can compare library families with the active Revit project and provides tools for reloading existing project families from the current Flow library.

---

## Review Project Status

Use the **Project Status** filter to review how library families relate to the active project.

| Status | Meaning |
| --- | --- |
| **Loaded** | The family is loaded in the active project |
| **Not Loaded** | The family is not loaded in the active project |
| **In Use** | At least one instance of the family is placed |
| **Unused** | The family is loaded but has no placed instances |

These filters can be combined with search, category, favourites and recent-content filters.

---

## Reload One Family

Use **Reload Family** when you want to update one already-loaded project family from the Flow library.

1. Find the required family in Content Browser.
2. Confirm that it shows as loaded in the project.
3. Right-click the family.
4. Select **Reload Family**.
5. Review the reload result.

**Reload Family** is only available for Revit family content that is already loaded into the active project.

Flow finds the family in the current Revit-version library using the family name and reloads it into the project.

!!! warning "Family parameter values are overwritten"

    Reloading uses the library family as the source and allows existing family parameter values to be overwritten.

    Use the reload action when the project family should be brought back into line with the current library version.

If the matching family cannot be found in the library, the reload result reports it as **Not found**.

---

## Reload Project Families

Use **Reload Project Families** when several categories of loaded project families should be refreshed from the Flow library.

1. Open **Tools**.
2. Select **Reload Project Families**.
3. Select the family categories to check.
4. Click **Continue**.
5. Flow compares the loaded project families in those categories with the current library.
6. Families found in the library are reloaded.
7. Review the completion summary.

The category picker includes:

- Annotation Symbols
- Casework
- Detail Items
- Doors
- Furniture
- Generic Models
- Plumbing Fixtures
- Profiles
- Site
- Specialty Equipment
- Windows

**Doors**, **Generic Models** and **Windows** are selected by default.

!!! info "Only matching loaded families are reloaded"

    Flow first identifies families already loaded in the active project for the selected categories.

    It then matches those family names against `.rfa` files in the current Flow library. Project families that do not have a matching library family are reported rather than reloaded.

---

## Reload Results

The reload result reports:

- families updated;
- families not found in the library;
- errors encountered while reloading.

For a category-based reload, Flow can also report how many project families were found in the library and which family names were missing.

---

## No Matching Families Are Found

If **Reload Project Families** reports that no matching loaded families were found:

1. Confirm that the correct Revit project is active.
2. Confirm that the expected families are actually loaded.
3. Check that the relevant family categories were selected.
4. Confirm that the families are part of the current Flow content library.

---

## Related Help

- [**Content Browser**](index.md)
- [**Browsing and Searching**](browsing-and-searching.md)
- [**Loading Content**](loading-content.md)
- [**Content Actions**](content-actions.md)
- [**Content Browser Tools**](content-browser-tools.md)
- [**Troubleshooting**](troubleshooting.md)