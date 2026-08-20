# Generating Catalogues

Use **Type Catalog Manager** to generate a Revit type catalogue from the types and parameters contained in a family.

Flow creates a catalogue row for each family type and allows you to choose which eligible parameters are included.

---

## Generate from an Open Family

When working directly in Type Catalog Manager, first open the required Revit family.

Then:

1. Open **Type Catalog Manager**.
2. Choose **Generate Catalogue**.
3. Select the parameters to include.
4. Click **Generate**.
5. Choose the location and file name for the `.txt` catalogue.
6. Save the catalogue.

The generated catalogue is loaded into Type Catalog Manager and validated automatically.

!!! warning "A family document is required"

	When generating directly from Type Catalog Manager, the active Revit document must be a family.

	If a project or no suitable family document is active, Flow asks you to open a family document.

---

## Choose Catalogue Parameters

The **Parameter Selection** window lists the family parameters that can be included in the generated catalogue.

Use the checkboxes to select the required parameters.

You can also:

* search for a parameter by name;
* use **Check All**;
* use **Uncheck All**;
* apply a saved parameter preset.

Some commonly used parameters are initially selected automatically where their names include terms such as width, height, depth, length, material or diameter.

---

## Parameters Excluded Automatically

Flow excludes family parameters that should not be driven by a type catalogue.

This includes:

* formula-driven parameters;
* reporting parameters.

These parameters are not offered for catalogue generation.

!!! info "Only eligible parameters are shown"

	Excluded parameters are filtered automatically so they cannot accidentally be written as catalogue inputs.

---

## Use a Parameter Preset

Parameter presets allow a commonly used group of catalogue parameters to be selected together.

1. Choose a preset from the preset list.
2. Apply the preset.
3. Review the selected parameters.
4. Add or remove individual parameters if required.
5. Continue with **Generate**.

Flow includes default presets for common content including windows and doors.

---

## Save a Parameter Preset

If you regularly use the same parameter combination:

1. Select the required parameters.
2. Choose **Save Preset**.
3. Enter a preset name.
4. Save the preset.

If a preset with the same name already exists, Flow asks whether you want to replace it.

Saved presets can then be reused during future catalogue generation.

---

## How the Catalogue Is Built

The first catalogue column represents the **Type Name**.

For each Revit family type, Flow creates a row containing:

1. the family type name; and
2. the values for each selected parameter.

The generated `.txt` file is then loaded back into Type Catalog Manager for review.

---

## Generate from Content Browser

You can also generate a catalogue directly from a library family in **Content Browser**.

Use the **Generate Type Catalog** action for the required family.

Flow opens the family for the generation process and launches Type Catalog Manager with the family ready for parameter selection.

This means you do not need to manually open the family before starting generation from Content Browser.

!!! tip "Use Content Browser for library content"

	When working with an existing library family, starting generation from **Content Browser** avoids having to locate and open the `.rfa` separately.

---

## After Generation

Review the generated catalogue before relying on it.

Check:

* the included parameters;
* the generated type names;
* the parameter values;
* the Validation panel.

You can then edit the catalogue normally if required.

---

## Related Help

* [**Type Catalog Manager**](index.md)
* [**Opening and Reviewing Catalogues**](opening-and-reviewing.md)
* [**Editing Catalogues**](editing-catalogues.md)
* [**Validation and Inspection**](validation-and-inspection.md)
* [**Troubleshooting**](troubleshooting.md)