# Generating Catalogues

Use **Type Catalogue Manager** to generate a Revit type catalogue from the types and parameters contained in a family.

Flow creates one catalogue row for each family type and allows you to choose which eligible type parameters are included.

---

## Choose a Generation Workflow

There are two ways to generate a catalogue.

### Open family workflow

Use this when the family is already open in Revit and you want to choose where the new catalogue is saved.

### Content Browser workflow

Use this when the family is stored in the content library and you want Flow to manage opening the family and creating its associated catalogue.

---

## Generate from an Open Family

The active Revit document must be a family document.

Then:

1. Open **Type Catalogue Manager**.
2. Choose **Tools → Generate Catalogue**.
3. Review the **Select Parameters** window.
4. Choose a parameter preset if appropriate.
5. Add or remove individual parameter selections as required.
6. Choose **Generate**.
7. Select the destination and file name for the `.txt` catalogue.
8. Confirm replacement if the destination already contains a file with the same name.
9. Review the generated catalogue in Type Catalogue Manager.

The generated catalogue is validated automatically.

!!! warning "A family document is required"

    Direct generation uses the active Revit family.

    If a project document is active instead, Flow asks you to open a family document before generating the catalogue.

---

## Select Catalogue Parameters

The **Select Parameters** window contains the family parameters that can be used as type-catalogue inputs.

Some commonly used parameters are selected automatically when their names contain terms such as:

* width;
* height;
* depth;
* length;
* material;
* diameter.

Review the selection rather than assuming every automatically selected parameter is required.

<!-- SCREENSHOT: Select Parameters window with a category-relevant preset active.
Show the Preset selector, compressed parameter list, Search,
Check All, Uncheck All, Save As Preset and Generate buttons. -->

---

## Parameters Excluded Automatically

Flow removes parameters that should not be driven by the generated type catalogue.

This includes:

* instance parameters;
* formula-driven parameters;
* reporting parameters.

These parameters are not available for selection.

!!! info "Only eligible type inputs are offered"

    Excluding non-type and calculated parameters prevents them from being written as catalogue input columns accidentally.

---

## Use Parameter Presets

Parameter presets make common parameter selections faster and more consistent.

Where presets are associated with the current family category, Flow presents the relevant options in the preset selector.

To use a preset:

1. choose the required preset;
2. Flow applies it immediately;
3. the visible parameter list is reduced to the parameters included in that preset;
4. review the checked parameters;
5. adjust individual selections if required;
6. choose **Generate** when ready.

There is no separate **Apply** button.

Default presets are available for common family categories including windows and doors.

---

## Show the Full Parameter List

Choose **All Parameters** when you need to return from a preset to the complete list of eligible family parameters.

**All Parameters** controls which parameters are visible. It does not mean that every parameter is automatically checked.

Use **Check All** if you want every currently displayed parameter selected.

<!-- SCREENSHOT: Optional second Select Parameters image.
Show All Parameters selected with the complete eligible list visible,
making it clear that All Parameters is a view/filter choice rather than Check All. -->

---

## Search for a Parameter

Use **Search parameters...** to filter the currently displayed parameter list by name.

Search works together with the active preset view.

For example, if a window preset is active, search filters the parameters within that preset selection.

Choose **All Parameters** first if you need to search the entire eligible parameter list.

---

## Check All and Uncheck All

**Check All** selects every parameter currently visible in the list.

**Uncheck All** clears every parameter currently visible in the list.

If a preset or search is filtering the list, these commands apply to the displayed parameters.

---

## Save a Parameter Preset

If you regularly generate catalogues using the same parameter combination:

1. select the required parameters;
2. choose **Save As Preset**;
3. enter a preset name;
4. save the preset.

If a preset with the same name already exists, Flow asks whether you want to replace it.

The saved preset is available for future catalogue-generation workflows and can be associated with the relevant family category.

---

## How the Catalogue Is Built

The first catalogue field represents the family **Type Name**.

For each Revit family type, Flow creates a row containing:

1. the family type name; and
2. the value of each selected parameter.

Parameter headers retain the Revit data type and unit information required by the type-catalogue format.

After generation, Flow loads the new `.txt` file into Type Catalogue Manager and validates it automatically.

---

## Generate from Content Browser

You can generate a catalogue without manually opening a library family.

In **Content Browser**:

1. locate the required `.rfa` family;
2. choose **Generate Type Catalog**;
3. Flow opens the family temporarily;
4. choose the parameters to include;
5. choose **Generate**;
6. confirm replacement if an associated catalogue already exists;
7. review the generated catalogue in Type Catalogue Manager.

The generated `.txt` catalogue is associated with the family and uses the corresponding family location and base file name.

For example:

`ADa_Window_Awning.rfa`

creates:

`ADa_Window_Awning.txt`

Flow closes the temporary family document when the generation process is complete.

!!! tip "Use Content Browser for library content"

    This workflow is the quickest option when creating or rebuilding a catalogue for a family that already exists in the Flow content library.

---

## After Generation

Before relying on the new catalogue, review:

* the included parameters;
* the Type Names;
* generated parameter values;
* units and data types where relevant;
* the **Validation** panel.

You can then edit the catalogue normally if adjustments are required.

---

## Related Help

* [**Type Catalogue Manager**](index.md)
* [**Opening and Reviewing Catalogues**](opening-and-reviewing.md)
* [**Editing Catalogues**](editing-catalogues.md)
* [**Validation and Inspection**](validation-and-inspection.md)
* [**Conforming Catalogues**](conforming-catalogues.md)
* [**Troubleshooting**](troubleshooting.md)
