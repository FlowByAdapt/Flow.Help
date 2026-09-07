# Door Heights

Use **Door Heights** to standardise the heights of New Doors by project level.

Flow creates or reuses appropriately sized Door types, then changes applicable Door instances to those types.

---

## Open Door Heights

From Openings Manager, click **Door Heights**.

Flow opens the Door Height settings workflow and identifies project levels that contain Doors.

For each populated level, the settings show:

- the level
- the number of Doors on that level
- the proposed target height

<!-- SCREENSHOT: Door Heights window showing several project levels and proposed heights. -->

---

## Proposed Heights

For each level containing Doors, Flow reviews the existing Door types and reads their:

```text
Panel Height
```

The most common usable Panel Height on that level becomes the proposed height.

If Flow cannot determine a usable Panel Height, it falls back to:

- **2200 mm** for the first populated level
- **1980 mm** for subsequent populated levels

Levels are evaluated in elevation order.

!!! tip "Review the proposed values"

    The proposed heights are starting values for the operation.

    Check each level and adjust the target height where the project requires something different.

---

## Apply Door Heights

A typical workflow is:

1. Click **Door Heights**.
2. Review the levels containing Doors.
3. Check the proposed height for each level.
4. Adjust any required values.
5. Apply the operation.
6. Review the result.
7. Return to the Opening Register.

When Door Heights is launched from Openings Manager, the register is refreshed after the workflow completes.

---

## New Doors Only

Door Height adjustment is intended for New Doors.

Flow skips Doors classified as:

- Existing
- Demolished

This prevents the standard New-Door height workflow from altering Existing or Demolished Door types through those instances.

!!! note

    The initial level counts and proposed-height calculation are based on Doors present on each level.

    Phase eligibility is checked when the height changes are applied.

---

## How Flow Changes a Door

Flow does not simply edit the existing Door type's Panel Height in place.

For each applicable Door, it:

1. reads the current type's **Panel Width**
2. combines that width with the target height for the Door's level
3. creates the required standard type name
4. searches for that type within the **same Door family**
5. reuses the type if it already exists
6. otherwise duplicates the current type
7. sets the duplicated type's **Panel Height**
8. changes the Door instance to the resulting type

This avoids changing the height of every Door already using the source type.

---

## Door Type Naming

The required type name is:

```text
<width>w x <height>h
```

For example:

```text
810w x 2200h
```

Panel Width and Panel Height are converted to millimetres and rounded to whole millimetres for the type name.

A Door with an 810 mm Panel Width and a target height of 2200 mm therefore uses:

```text
810w x 2200h
```

---

## Reusing Existing Types

Before creating a new type, Flow searches within the current Door family for an existing type with the required name.

The family name and type name must match.

If the required type already exists, Flow reuses it rather than creating another duplicate.

If it does not exist, Flow attempts to duplicate the Door's current type and set its Panel Height to the required value.

---

## Required Door Parameters

The workflow depends on the Door type exposing usable parameters named:

```text
Panel Width
Panel Height
```

**Panel Width** is required to calculate the standard type name.

**Panel Height** must be writable when Flow needs to create a new target type.

If these parameters are missing or unsuitable, the affected Door may not be updated.

---

## Opening Register Selection

The current **Door Heights** button in Openings Manager does **not** use the checked or filtered rows as its scope.

It launches the project Door Heights workflow and evaluates the project Doors by level.

!!! important "Checked Doors do not limit the dashboard workflow"

    Checking Door rows in the Opening Register before clicking **Door Heights** does not restrict the operation to those checked Doors.

    The current Openings Manager launch path supplies the project Door set to the Door Heights workflow.

This differs from commands such as **Standardise**, **Generate Views** and **Tag**, which provide explicit register-scope choices.

---

## Selected-Door Capability

The underlying Door Height service supports restricting an operation to a supplied set of Door IDs when a workflow explicitly provides that selection.

However, the current Door Heights launch from the Openings Manager dashboard does not pass the manager's checked-row selection into that mechanism.

For normal Openings Manager use, treat Door Heights as a project-level Door workflow rather than a checked-row command.

---

## What Happens if the Door Already Uses the Target Type?

If a Door already has the required target type, Flow does not need to change that instance again.

Likewise, when the required type exists elsewhere in the same family, Flow can reuse it directly.

This helps avoid unnecessary duplicate Door types.

---

## Failure Protection

Door type creation and assignment are performed through Revit transactions.

When Flow creates a new target type, Revit warnings encountered during that type-creation transaction are suppressed, while errors cause that type creation to roll back.

If a particular Door or type cannot be updated successfully, the workflow can continue processing the remaining Doors rather than requiring the entire project-level operation to succeed as one transaction.

---

## Result Information

The Door Height adjustment service tracks outcomes including:

- Doors processed
- Doors updated
- types created
- existing types reused
- Doors skipped because no Panel Width was available
- Doors skipped because no height setting existed for their level
- Existing or Demolished Doors skipped

A processed Door is not necessarily an updated Door. For example, it may already use the target type or may be skipped by one of the eligibility checks.

---

## If a Door Is Not Updated

Check that:

- the Door is New rather than Existing or Demolished
- its type contains a usable **Panel Width**
- the Door's level has a target height
- a new type can expose a writable **Panel Height**
- the required type can be created or found within the same Door family
- the Door does not already use the required target type

For further checks:

➡️ [**Openings Manager Troubleshooting**](troubleshooting.md)

---

## Recommended Workflow

For a project-wide Door height review:

1. Open the Opening Register and review the Doors.
2. Click **Door Heights**.
3. Review the proposed height for every populated level.
4. Change any level values required by the project.
5. Apply the operation.
6. Review the result.
7. Confirm the refreshed Opening Register.
8. Continue with Door documentation.

If the resulting Door type information affects existing Door elevations, use **Conform Views** where required.

➡️ [**Conforming Opening Views**](conforming-opening-views.md)

---

## Related Help

- [**Reviewing Openings**](reviewing-openings.md)
- [**Opening Marks**](opening-marks.md)
- [**Generating Opening Views**](generating-opening-views.md)
- [**Conforming Opening Views**](conforming-opening-views.md)
- [**Opening Global Parameters**](opening-global-parameters.md)
- [**Openings Manager Troubleshooting**](troubleshooting.md)
