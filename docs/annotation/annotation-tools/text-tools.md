# Text Tools

**Text Tools** provides common case-editing workflows for Revit Text Notes.

Flow can convert selected Text Notes to:

* **UPPER CASE**
* **lower case**
* **Sentence Case**
* **Title Case**

Sentence Case, Title Case and lower case include technical text-handling rules designed for architectural, BIM and documentation terminology.

**Ribbon:** **Flow → Annotation → Text Tools**

---

## When to Use Text Tools

Use **Text Tools** when existing Revit Text Notes need consistent capitalisation without editing each note manually.

Typical uses include:

* converting notes to uppercase
* converting notes to lowercase
* standardising notes to sentence case
* converting headings or labels to title case
* correcting inconsistent capitalisation across multiple Text Notes
* retaining recognised technical terminology while changing surrounding text

---

## Supported Views

Text Tools is available in:

* Floor Plans
* Reflected Ceiling Plans
* Engineering Plans
* Area Plans
* Sections
* Elevations
* Detail Views
* Drafting Views
* Sheets
* Legends

Text Tools is not available in View Templates or unsupported Revit view types.

---

## Changing Text Case

### 1. Choose the Case

Start:

**Flow → Annotation → Text Tools**

The **Choose text operation** window opens.

Choose:

* **UPPER CASE**
* **lower case**
* **Sentence Case**
* **Title Case**

<!-- Screenshot recommended:
Show the "Choose text operation" window with all four case options visible.
-->

### 2. Select Text Notes

If Text Notes were selected before starting Text Tools, Flow uses those notes automatically.

If the current selection contains a mixture of elements, valid Text Notes are used and other element types are ignored.

If no Text Notes are preselected, select Text Notes one at a time in the Revit view.

Press **Esc** when selection is complete.

!!! tip "Preselect multiple notes"

	For a quick bulk change, select the required Text Notes before opening Text Tools.

### 3. Apply the Change

Flow applies the selected case to each Text Note.

Text Notes whose content already matches the required result are left unchanged.

When the operation is complete, Text Tools finishes automatically.

To perform another case operation, start **Text Tools** again.

---

## Case Options

### UPPER CASE

Converts the complete Text Note to uppercase.

For example:

```text id="i6v1z4"
Install new wall lining
```

becomes:

```text id="dxh1yu"
INSTALL NEW WALL LINING
```

---

### lower case

Converts ordinary text to lowercase while retaining recognised technical terms in their defined format.

For example, recognised terms such as:

```text id="o2r5y1"
Revit
NZBC
BIM
FFL
```

retain their technical capitalisation rather than being converted blindly to lowercase.

---

### Sentence Case

Converts ordinary wording to sentence case while preserving recognised technical terminology and applicable tokens containing numbers.

For example:

```text id="myrq6u"
INSTALL NEW GIB LINING TO NZBC REQUIREMENTS
```

becomes:

```text id="l4x2nx"
Install new GIB lining to NZBC requirements
```

The first ordinary word is capitalised and subsequent ordinary words are lowercased.

---

### Title Case

Capitalises ordinary words while retaining recognised technical terminology and applicable tokens containing numbers.

For example:

```text id="r7pyxp"
install new GIB lining to NZBC requirements
```

becomes:

```text id="rfsj4x"
Install New GIB Lining To NZBC Requirements
```

!!! note "Technical title case"

	Title Case applies Flow's technical casing rules rather than attempting to apply grammatical title conventions such as automatically lowercasing minor words.

---

## Technical Terms

Text Tools recognises a collection of common architectural, BIM, software and technical terms that require specific capitalisation.

Examples include:

* Revit
* pyRevit
* CPython
* IronPython
* ADa
* NZBC
* NZS
* RFI
* PDF
* API
* BIM
* DWG
* IFC
* GIB
* FFL
* LVL
* HDMI
* PS1

Recognised terms are restored to their defined format when technical case rules are applied.

Text Tools also handles:

* applicable tokens containing numbers
* recognised terms within hyphenated expressions
* punctuation at the end of words

!!! info "Recognised terminology"

	Technical-term preservation applies to terminology recognised by Text Tools. An arbitrary word written in capitals is not automatically treated as a protected abbreviation.

---

## Text Formatting

Text Tools attempts to preserve supported character formatting while changing the case of a Text Note.

Supported formatting includes:

* **Bold**
* *Italic*
* Underline
* Superscript
* Subscript
* All Caps formatting

Flow records the character formatting before changing the text and reapplies it to the corresponding characters afterwards.

!!! note "Formatting preservation"

```
Formatting can be preserved when the transformed text can be mapped safely back to the original characters.

If Flow cannot safely retain the formatted-text structure, it falls back to updating the Text Note as plain text. In this situation, character-level formatting may not be retained.
```

For normal case changes, the number of characters will generally remain unchanged, allowing the existing formatting to be preserved.

---

## Selection

Text Tools supports both preselection and interactive selection.

### Preselection

If the current Revit selection contains one or more Text Notes when Text Tools starts, Flow uses those Text Notes.

Other selected element types are ignored.

Flow does not enter interactive selection when valid Text Notes are already preselected.

### Interactive Selection

If no Text Notes are preselected, Flow prompts:

> Select text notes to change. Press Escape when finished.

Only Text Notes can be selected.

Continue selecting notes until all required notes have been collected, then press **Esc**.

Selecting the same Text Note more than once does not add it to the operation again.

---

## If a Text Note Cannot Be Changed

Flow attempts to apply the selected case to every collected Text Note within a single operation.

If one or more Text Notes cannot be changed, Flow reports:

* how many Text Notes were successfully changed
* how many Text Notes could not be changed

If all selected Text Notes are processed without an individual failure, Text Tools finishes without displaying a completion message.

If the overall operation cannot be completed, the transaction is rolled back and Flow displays the reason where available.

---

## Related Help

* [Text Tools Troubleshooting](troubleshooting.md)
* [Annotation](index.md)