# Standardising Patterns

Use Pattern Manager’s naming tools to apply the ADa project naming format consistently to project fill patterns.

---

## Naming Behaviour

Flow standardises eligible names with the `ADa_` prefix. It trims surrounding whitespace and removes leading legacy markers before applying the prefix.

Existing variants such as `ADa_`, `ADa-`, `ADa `, `ADa:` and `ADa.` are removed before the correct prefix is applied. This prevents duplicated or retained legacy prefixes. Other characters in the pattern name are not generally sanitised.

Revit system patterns, including solid fill, are not processed as user-managed project patterns.

---

## Conform One Pattern Name

1. Open **ADAPT → Model → Patterns**.
2. Open **Project Patterns**.
3. Right-click the required pattern.
4. Select **Conform Name**.

Flow shows the current and proposed names for confirmation. Select **Conform** to rename the pattern. The project-pattern list then refreshes to show the result.

Use this option when you have reviewed a specific pattern and want to correct only that definition.

---

## Conform All Project Pattern Names

1. Open **Project Patterns**.
2. Open the project-pattern context menu.
3. Select **Conform Project Pattern Names...**.

Flow analyses all eligible project patterns and prepares the proposed naming changes.

---

## Review Proposed Changes

Before bulk changes are applied, review the proposed original and replacement names.

Patterns that already comply do not need to be renamed. Patterns that cannot be changed safely are left unchanged and reported rather than being silently forced into a conflicting name.

<!-- SCREENSHOT: Bulk conform confirmation showing several current names and proposed ADa_ names, including the summary counts. -->

Check particularly for:

- two source names that would produce the same standard name;
- a proposed name that already exists in the project; and
- a cleaned name that no longer describes the pattern clearly.

!!! note "Only the name changes"

    Flow renames the existing fill-pattern element. Its grid definition and project references remain unchanged. Review the proposed names before applying a bulk update where schedules or external coordination depend on recognisable names.

---

## Apply the Changes

Confirm the bulk operation after reviewing the preview.

Flow applies the valid changes and reports the outcome, including patterns that were renamed, already compliant, skipped or unable to be changed.

After completion, review the refreshed project-pattern list and its library-match status.

---

## Names Applied During Loading

The same standard naming service is used when a library pattern is loaded or duplicated into the project. This helps prevent newly introduced project patterns from bypassing the expected naming format.

---

## Related Help

- [Pattern Manager](index.md)
- [Project Patterns](project-patterns.md)
- [Browsing the Pattern Library](browsing-pattern-library.md)
- [Troubleshooting](troubleshooting.md)