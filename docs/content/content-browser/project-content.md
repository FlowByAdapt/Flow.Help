# Project Content

Content Browser compares indexed families with the active Revit project and provides tools for reloading existing project families from the current library.

---

## Review Project Status

| Status | Meaning |
| --- | --- |
| **Loaded** | At least one type of the family is loaded |
| **Not Loaded** | The family name was not detected in the active project |
| **In Use** | At least one family instance was detected |
| **Unused** | Types are loaded but no family instances were detected |

Status matching uses the family name and ignores capitalisation. Combine project status with search, category, favourites and recent-content filters as required.

---

## Reload One Family

Use **Reload Family** to update one loaded project family from the current Flow library.

1. Find the family and confirm that it shows as loaded.
2. Right-click it.
3. Select **Reload Family**.
4. Review the result message.

Flow matches the Revit family name against `.rfa` filenames below the current version-specific library root.

!!! warning "Family parameter values are overwritten"

    Reloading accepts the library family and allows existing family parameter values to be overwritten. The incoming source is also used for shared families.

If no matching file exists, the result reports **Not found**. If duplicate filenames exist in different library folders, Flow uses the first matching path it finds.

---

## Reload Project Families

Use **Reload Project Families** to refresh loaded families across selected categories.

1. Open **Tools**.
2. Select **Reload Project Families**.
3. Select one or more categories.
4. Click **Continue**.
5. Review the completion message.

Available categories are:

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

Flow finds loaded project families in those categories, matches their names against the library and reloads the matches independently. An error affecting one family does not prevent later matches from being attempted.

<!-- SCREENSHOT: Reload Families picker.
Show the complete category list with Doors, Generic Models and Windows selected. -->

---

## Reload Results

The final result reports:

- families updated;
- matching families not found during execution; and
- errors encountered while reloading.

If no selected project family matches the library, Flow reports **No matching loaded families were found.**

!!! note "Current missing-family reporting"

    When some families match and others are absent from the library, the final message may omit the names excluded during discovery. An absent name in the completion message does not prove that every selected project family had a library match.

---

## If No Matching Families Are Found

1. Confirm that the correct project is active.
2. Confirm that the expected families are loaded.
3. Check the selected family categories.
4. Confirm that matching `.rfa` filenames exist in the current Revit-version library.

---

## Getting Help

Hover over **Browser** on the Flow ribbon and press **F1** to open the Content Browser help.

---

## Related Help

- [**Content Browser**](index.md)
- [**Browsing and Searching**](browsing-and-searching.md)
- [**Loading Content**](loading-content.md)
- [**Content Actions**](content-actions.md)
- [**Content Browser Tools**](content-browser-tools.md)
- [**Troubleshooting**](troubleshooting.md)
