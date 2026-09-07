# Type Catalogue Manager Troubleshooting

Use the following checks if Type Catalogue Manager or a type catalogue is not behaving as expected.

---

## Type Catalogue Manager Is Not Open

Open Type Catalogue Manager from the Revit ribbon:

**Flow → Content → Types**

You can also search for **Type Catalogue Manager** using the **Command Palette**.

---

## A Catalogue Cannot Be Opened

Confirm that:

1. the `.txt` file still exists;
2. you have access to its location;
3. the file contains a valid type-catalogue header;
4. the file contains catalogue row data;
5. the file has not been damaged or replaced with unrelated text content.

Type Catalogue Manager requires a readable Revit type catalogue before it can populate the grid.

---

## The Catalogue Shows Validation Issues

Review the **Validation** panel and select an issue to navigate to the affected data.

Common problems include:

* empty column headers;
* duplicate column headers;
* duplicate Type Names;
* missing values;
* empty values.

See [**Validation and Inspection**](validation-and-inspection.md).

---

## A Catalogue Contains Structural Problems

Use **Conform Catalogue** where the catalogue has structural conditions that Flow can resolve safely.

Conform can repair catalogue structure while preserving existing Revit parameter header definitions.

Blank and duplicate Type Names still require a user decision.

See [**Conforming Catalogues**](conforming-catalogues.md).

---

## A Duplicated Row Shows an Error

Duplicating a row copies all of its values, including its **Type Name**.

Change the copied row to a unique Type Name.

Duplicate Type Names are reported as validation errors.

---

## Changes Have Not Been Saved

When a catalogue has been edited, Type Catalogue Manager identifies it as having **Unsaved Changes**.

Use **Save** to update the active catalogue or **Save As** to create and continue working with a separate file.

If you close or reload while unsaved changes exist, Flow asks how you want to proceed.

---

## Generate Catalogue Does Not Work

When generating directly from Type Catalogue Manager, make sure the active Revit document is a **family document**.

If you are working with a family in the content library, use **Generate Type Catalog** from Content Browser instead.

---

## A Parameter Is Missing from Catalogue Generation

Flow does not offer parameters that are unsuitable for use as type-catalogue inputs.

The excluded parameters include:

* instance parameters;
* formula-driven parameters;
* reporting parameters.

If the parameter is an eligible type parameter, choose **All Parameters** and use the parameter search to locate it.

---

## A Preset Does Not Show a Parameter

A preset only displays parameters included in that preset and available in the current family.

Choose **All Parameters** to return to the complete eligible parameter list.

You can then:

1. search for the required parameter;
2. select it;
3. update or save a preset if the parameter should be included in future workflows.

---

## All Parameters Did Not Check Everything

**All Parameters** changes the parameter list from a preset-filtered view to the complete eligible list.

It is not the same as **Check All**.

Choose **Check All** if every currently displayed parameter should be selected.

---

## Content Browser Cannot Edit a Catalogue

The selected library family must have an associated `.txt` type catalogue with the same base file name.

For example:

`ADa_Door_Single.rfa`

requires:

`ADa_Door_Single.txt`

If no associated catalogue is found, generate a new catalogue where appropriate.

---

## Content Browser Cannot Conform a Catalogue

The selected family must have an associated type catalogue.

If no catalogue is found, Flow reports:

**No type catalogue found for this family.**

Generate a catalogue first if the family requires one.

---

## Content Browser Generation Wants to Replace a File

Content Browser generation creates the catalogue associated with the selected family.

If a catalogue with that name already exists, Flow asks whether you want to replace it.

Review the existing file before confirming replacement if you need to preserve manual catalogue changes.

---

## Reloading a Catalogue

**Reload** reads the current catalogue from disk.

If the Manager contains unsaved changes, Flow asks how you want to proceed before reloading.

Choose **Cancel** if you are not ready to discard or save the current edits.

---

## Validation Does Not Match the Family

Type Catalogue Manager validates the catalogue itself. It does not perform a complete comparison against the family definition.

Validation does not prove that:

* every catalogue parameter exists in the family;
* every eligible family parameter is present in the catalogue;
* catalogue values create the intended family geometry.

Where required, review or test the catalogue with its Revit family.

---

## Still Having Problems?

Confirm that the family and catalogue files are available and that you have permission to access their storage location.

If the catalogue opens successfully, use the **Validation** panel to identify catalogue-data problems before making further changes.

---

## Related Help

* [**Type Catalogue Manager**](index.md)
* [**Opening and Reviewing Catalogues**](opening-and-reviewing.md)
* [**Editing Catalogues**](editing-catalogues.md)
* [**Validation and Inspection**](validation-and-inspection.md)
* [**Conforming Catalogues**](conforming-catalogues.md)
* [**Generating Catalogues**](generating-catalogues.md)
