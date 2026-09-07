# Worksets

**Worksets** checks the worksets in a workshared Revit project against the standard configuration expected for the project's model role.

Flow determines whether the project is a **Main Project** or **Topography** model, identifies any required workset changes and allows you to review the proposed configuration before applying it.

Existing unrelated worksets are preserved.

**Ribbon:** **Flow → Project → Setup**

---

## When to Use Worksets

Use the **Worksets** workflow when:

* worksharing has been enabled on a new project
* reviewing the worksets in an existing workshared project
* standard Flow worksets are missing
* the initial Revit workset needs to be renamed
* Flow cannot determine whether an existing project is a Main Project or Topography model

---

## Before You Start

The active Revit project must be workshared before Flow can configure its worksets.

If the project is not yet workshared, complete the [Worksharing](worksharing.md) workflow first.

!!! info "Worksets depend on the model role"

	Flow does not apply one identical workset list to every project.

	The expected configuration depends on whether the model is a **Main Project** or **Topography** model.

---

## Inspecting Worksets

### 1. Inspect the Project

Open:

**Flow → Project → Setup**

Select **Inspect Project**.

If the project is workshared, Flow inspects the existing worksets.

### 2. Flow Determines the Model Role

Where the model role is already known, Flow uses it to determine the expected workset configuration.

If Flow cannot resolve the role, it inspects the existing worksets but does not assume which role should be applied.

### 3. Review the Worksets Status

Review the **Worksets** card in the Current Project area.

The status indicates whether the existing worksets meet the expected configuration or whether changes are required.

<!-- Screenshot recommended:
Show the Worksets card after inspection where configuration is required.
Where practical, include the model role and the Configure Worksets action.
-->

---

## If the Model Role Is Unknown

If the project is workshared but its model role cannot be determined, Flow asks you to identify the model as:

* **Main Project**
* **Topography**

Choose the role that describes the Revit model being configured.

Flow records the selected role and reinspects Project Setup using the expectations for that model type.

<!-- Screenshot recommended:
Show the Main Project / Topography role selection window.
This is useful because the choice directly controls the workset configuration that Flow expects.
-->

!!! important "Choose the correct model role"

	The selected role determines which standard worksets Flow expects.

	Do not select a role simply to clear the Worksets status.

	Choose the role that represents the actual purpose of the Revit model.

---

## Main Project Worksets

For a **Main Project** model, Flow expects the standard worksets configured for the main building model.

The current configuration includes:

* **ADa_Workset1**
* **ADa_Topo**

Flow compares the existing project against these expectations before proposing changes.

---

## Topography Worksets

For a **Topography** model, Flow expects:

* **ADa_Workset1**
* **ADa_Building**
* **ADa_CAD**
* **ADa_Survey**

Flow compares the existing project against these expectations before proposing changes.

!!! info "Configuration can evolve"

	The workset configuration is controlled by Project Setup rather than by this Help page.

	If your installed Flow configuration differs from the examples above, follow the configuration preview shown by Flow.

---

## Configuring Worksets

### 1. Review the Inspection Result

Check the Worksets status after **Inspect Project** has completed.

If changes are required, select **Configure Worksets**.

### 2. Review the Proposed Configuration

Flow prepares a configuration plan before changing the project.

The preview identifies:

* the model role
* any initial workset rename
* worksets that need to be created

Review the proposed changes before continuing.

<!-- Screenshot recommended:
Show the Workset configuration preview immediately before confirmation.
The model role, proposed rename and worksets to be created should be visible.
-->

### 3. Confirm the Configuration

Confirm the workset configuration.

Flow then applies the required changes to the active Revit project.

### 4. Flow Reinspects the Project

After successful configuration, Flow automatically reinspects Project Setup.

The Worksets status is recalculated from the resulting project state.

---

## Renaming the Initial Workset

When appropriate, Flow can rename Revit's initial user workset to:

**ADa_Workset1**

The proposed rename is included in the configuration preview before changes are applied.

Flow does not silently rename arbitrary existing worksets.

---

## Creating Missing Worksets

If an expected standard workset does not exist, Flow can create it as part of the configuration.

Only the worksets required by the selected model role are included in the plan.

Existing standard worksets that already satisfy the expectation do not need to be recreated.

---

## Existing Worksets Are Preserved

Flow does not delete unrelated existing worksets as part of standard workset configuration.

The workflow is intended to establish the expected Flow worksets without removing additional worksets that may legitimately exist in the project.

!!! info "Configuration is additive"

	Flow can rename the expected initial workset and create missing standard worksets.

	It does not use the configuration operation as a general workset cleanup tool.

---

## Expected Result

After successful Workset configuration:

* the project's model role is resolved
* the expected standard worksets for that role are present
* the initial workset has been renamed where required
* unrelated existing worksets remain in the project
* Flow automatically reinspects Project Setup
* the Worksets status reflects the resulting configuration

---

## If Configure Worksets Is Unavailable

### Worksharing Is Not Enabled

Complete the [Worksharing](worksharing.md) workflow first.

### The Project Has Not Been Inspected

Select **Inspect Project**.

### The Model Role Is Unknown

Choose **Main Project** or **Topography** when prompted so Flow can determine the expected worksets.

### No Changes Are Required

If the existing worksets already meet the expected configuration, no configuration action is required.

---

## If a Workset Already Exists

Flow inspects the existing project before preparing the configuration plan.

A standard workset that already exists does not need to be created again.

The preview should therefore reflect only the changes required by the current project state.

---

## If Additional Worksets Exist

Additional worksets do not need to be removed simply because they are not part of the standard Flow expectation.

Flow preserves unrelated existing worksets during standard configuration.

If an additional workset is no longer required, manage that separately rather than expecting Project Setup to delete it.

---

## Related Help

* [Project Setup](index.md)
* [Reviewing a Current Project](current-projects.md)
* [Worksharing](worksharing.md)
* [Project Setup Troubleshooting](troubleshooting.md)