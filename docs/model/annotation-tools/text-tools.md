# Text Tools

**Text Tools** provides common editing workflows for Revit Text Notes.

The verified text-case workflow changes selected Text Notes to one of four supported case formats:

-   **UPPER**
-   **lower**
-   **Sentence Case**
-   **Title Case**

------------------------------------------------------------------------

## Opening the Tool

On the **Flow** ribbon:

1.  Open **Annotation**.
2.  Choose **Text Tools**.

------------------------------------------------------------------------

## Changing Text Case

1.  Start **Text Tools**.
2.  Choose the required text case.
3.  Use preselected Text Notes, or select Text Notes in the Revit view.
4.  Press **Esc** when you have finished selecting notes.
5.  Flow applies the selected case.
6.  Choose whether to repeat, change mode or exit.

------------------------------------------------------------------------

## Case Options

### UPPER

Converts the selected text to uppercase.

Example:

`Install new wall lining`

becomes:

`INSTALL NEW WALL LINING`

### lower

Converts the selected text to lowercase.

### Sentence Case

Formats the text as technical sentence case while preserving recognised technical abbreviations and words.

### Title Case

Capitalises words using the technical title-case rules while preserving recognised abbreviations.

------------------------------------------------------------------------

## Technical Terms

The source workflow contains a preservation list for common architectural, BIM and technical terms such as:

-   Revit
-   pyRevit
-   NZBC
-   NZS
-   BIM
-   DWG
-   IFC
-   FFL
-   GIB
-   LVL
-   HDMI

It also preserves all-capital tokens, tokens containing numbers and recognised hyphenated technical terms.

------------------------------------------------------------------------

## Text Formatting

The verified source workflow rewrites changed Text Notes as plain formatted text.

!!! warning "Rich text formatting"

    The verified source workflow removes rich-text formatting such as **bold**, *italic* and underline from a Text Note when its case is changed.

------------------------------------------------------------------------

## Selection

Text Tools supports preselected Revit Text Notes.

If no valid Text Notes are preselected, the workflow allows notes to be picked one by one until **Esc** is pressed.

Duplicate picks are ignored.

------------------------------------------------------------------------

## Related Help

-   [Text Tools Troubleshooting](troubleshooting.md)
-   [Annotation](index.md)