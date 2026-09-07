# Worksharing

**Worksharing** checks whether the active Revit project is workshared and, where required, allows Flow to enable worksharing as part of Project Setup.

Enabling worksharing is a separate step from configuring the standard Flow worksets. Once worksharing has been enabled, Flow reinspects the project so the required workset configuration can be assessed.

**Ribbon:** **Flow → Project → Setup**

---

## When to Use Worksharing

Use the **Worksharing** workflow when:

* setting up a new project that will be workshared
* reviewing an existing project that is not yet workshared
* preparing a project before configuring standard Flow worksets

If the project is already workshared, Flow reports its current state and no enablement action is required.

---

## Before You Start

Open or activate the Revit project you want to configure.

Select **Inspect Project** so Flow can determine the current worksharing state.

!!! info "Worksharing and Worksets are separate"

	Enabling Worksharing allows the Revit project to use worksets.

	It does not complete the standard Flow workset configuration.

	After worksharing is enabled, use the **Worksets** workflow to review and configure the expected project worksets.

---

## Enabling Worksharing

### 1. Inspect the Project

Open:

**Flow → Project → Setup**

Select **Inspect Project**.

Flow checks whether the active Revit project is already workshared.

### 2. Review the Worksharing Status

Review the **Worksharing** card in the Current Project area.

If worksharing has not been enabled, the card identifies that the project requires attention and provides the option to enable it.

<!-- Screenshot recommended:
Show the Current Project area after inspection with Worksharing requiring attention.
Include the Worksharing card and Enable Worksharing action.
-->

### 3. Select Enable Worksharing

Select **Enable Worksharing**.

Flow displays a confirmation before changing the Revit project.

Review the message and confirm the operation.

### 4. Flow Enables Worksharing

Flow asks Revit to enable worksharing in the active project.

Revit creates the initial worksharing structure required by the project.

### 5. Flow Reinspects the Project

After worksharing has been enabled successfully, Flow automatically reinspects Project Setup.

The Worksharing status is updated and the **Worksets** workflow can then assess the project's worksets.

---

## Expected Result

After successful worksharing enablement:

* the active Revit project is workshared
* Revit has created its initial worksharing structure
* Flow has automatically reinspected the project
* the Worksharing status reflects the new project state
* Worksets can be reviewed and configured

Enabling worksharing does not itself complete the standard Flow workset configuration.

---

## Revit's Initial Worksets

When worksharing is first enabled, Revit creates the initial worksets required for a workshared project.

These should not be confused with the standard worksets expected by Flow.

The subsequent **Worksets** workflow compares the resulting project against the workset configuration expected for the project's model role.

See [Worksets](worksets.md).

---

## If the Project Is Already Workshared

If Flow finds that the project is already workshared, **Enable Worksharing** is not required.

Continue to the **Worksets** area to check whether the expected workset configuration is present.

---

## If Enable Worksharing Is Unavailable

### The Project Has Not Been Inspected

Select **Inspect Project** first so Flow can determine the current worksharing state.

### The Project Is Already Workshared

No enablement action is required.

Continue to the Worksets workflow.

### No Project Is Active

Open or activate a Revit project and inspect it again.

---

## If Worksharing Cannot Be Enabled

If Revit cannot enable worksharing, Flow reports the operation as unsuccessful.

The project is not treated as successfully configured.

Review any information reported by Flow or Revit, correct the underlying issue and try again.

---

## Continuing with Worksets

After worksharing has been successfully enabled, review the **Worksets** status.

Flow can then:

1. determine the project's model role
2. identify the expected worksets for that role
3. inspect the existing worksets
4. preview any required changes
5. configure the missing or incorrectly named standard worksets

See [Worksets](worksets.md).

---

## Related Help

* [Project Setup](index.md)
* [Reviewing a Current Project](current-projects.md)
* [Worksets](worksets.md)
* [Project Setup Troubleshooting](troubleshooting.md)