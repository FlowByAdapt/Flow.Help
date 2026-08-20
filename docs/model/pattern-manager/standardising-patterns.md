# Standardising Patterns

Use Pattern Manager’s naming tools to apply the ADa project naming format consistently to project fill patterns.

---

## Naming Behaviour

Flow standardises eligible names with the `ADa_` prefix and removes or replaces characters that are not suitable for the project naming format.

Existing variants of the prefix are normalised before the correct prefix is applied. This prevents results such as duplicated `ADa_` prefixes or a retained `ADa-` prefix.

Revit system patterns, including solid fill, are not processed as user-managed project patterns.

---

## Conform One Pattern Name

1. Open **Flow → Model → Patterns**.
2. Open **Project Patterns**.
3. Right-click the required pattern.
4. Select **Conform Name**.

Flow calculates and applies the standard name to that pattern. The project-pattern list then refreshes to show the resulting name.

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

Check particularly for:

- two source names that would produce the same standard name;
- a proposed name that already exists in the project; and
- a cleaned name that no longer describes the pattern clearly.

!!! warning "Names can be referenced elsewhere"

    Renaming changes the project fill-pattern definition. Review the proposed list before applying a bulk update, particularly where office standards, schedules or external coordination depend on recognisable pattern names.

---

## Apply the Changes

Confirm the bulk operation after reviewing the preview.

Flow applies the valid changes and reports the outcome, including patterns that were renamed, already compliant, skipped or unable to be changed.

After completion, review the refreshed project-pattern list and its library-match status.

---

## Names Applied During Loading

The same standard naming service is used when a library pattern is loaded or a project pattern is updated. This helps prevent newly introduced project patterns from bypassing the expected naming format.

---

## Related Help

- [Pattern Manager](index.md)
- [Project Patterns](project-patterns.md)
- [Browsing the Pattern Library](browsing-pattern-library.md)
- [Troubleshooting](troubleshooting.md)