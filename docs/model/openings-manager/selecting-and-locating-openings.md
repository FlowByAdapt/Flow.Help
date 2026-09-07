# Selecting and Locating Openings

The Openings Manager register is connected to the active Revit model.

Use the selection and navigation controls to move between the register and Revit, build a working selection and inspect openings before running a command.

---

## Register Rows and Checkboxes

There are two different types of selection in the Opening Register.

### Highlight a Row

Click a row in the register to make it the current opening.

The corresponding Revit element is selected immediately.

Use this when reviewing individual openings or when you want to identify which model element a register row represents.

### Check an Opening

Use the checkbox at the left of a row to add that opening to the Manager's **working selection**.

Checked openings are used by scoped commands such as:

- **Standardise**
- **Generate Views**
- **Tag**

!!! important "A highlighted row is not the same as a checked opening"

    Highlighting a row identifies the current opening and selects it in Revit.

    Checking a row adds it to the working selection used by applicable Openings Manager commands.

<!-- SCREENSHOT: Opening Register showing one highlighted row and several checked rows. Keep the Selection toolbar and filters visible. -->

---

## Zoom to an Opening

Double-click a register row to locate that opening in Revit.

Flow uses the opening's Element ID to focus the corresponding element in the active Revit context.

This is useful when an opening has an unexpected mark, Global Parameter status or other issue and you want to inspect it directly in the model.

---

## Select Openings from the Model

Use **Select from Model** when the openings are easier to identify graphically than in the register.

1. Click **Select from Model**.
2. Flow switches Revit to **3D-01-Work Main**.
3. Pick the required elements in Revit.
4. Finish the Revit selection.
5. Matching openings are checked in the Opening Register.

Flow briefly highlights the matching register rows so they are easy to identify.

!!! note "Required 3D view"

    The project must contain a view named exactly **3D-01-Work Main** for **Select from Model** to start.

    Flow does not automatically return to the view that was active before the selection workflow.

Only elements represented by the Opening Register become checked openings. If an unrelated model element is picked, it does not become an Opening Manager record.

<!-- SCREENSHOT: Revit 3D-01-Work Main with model selection active or just completed, alongside the Manager showing the corresponding checked/highlighted rows. -->

---

## Select Filtered Openings

Use **Select Filtered** to check every opening currently displayed by the register filters.

For example:

1. Set **Category** to Windows.
2. Set the required **Level**.
3. Set **Phase** as required.
4. Apply any additional search or status filters.
5. Click **Select Filtered**.

The visible filtered records become the working selection.

This is useful when you want to process a defined group rather than selecting openings individually.

!!! important "Set filters before checking openings"

    Changing **Category**, **Level**, **Phase** or **GP Status** clears the current checked selection.

    Apply the required filters first, then check individual openings or use **Select Filtered**.

---

## Focus an Opening

Use **Focus** to locate one opening in Revit.

Flow uses:

1. the currently highlighted register row, or
2. the first checked opening if no row is highlighted.

**Focus does not frame all checked openings at once.**

Use it when you have identified an opening in the register and want to inspect that individual element in the model.

---

## Clear the Register State

Use **Clear** when you want to reset the current register filtering/selection state before building a new working set.

After clearing, review the register before running a scoped command to make sure the intended openings are checked or visible.

---

## Checked, Filtered or All?

Several commands ask which part of the Opening Register should be processed.

Depending on the current register state, the scope chooser can offer:

- **Checked** — openings explicitly checked in the register
- **Filtered** — openings currently passing the register filters
- **All** — all openings in the register

The exact scope options are command-specific.

### Commands that use register scope

The main scoped workflows are:

- **Standardise**
- **Generate Views**
- **Tag**

### Commands with their own selection workflow

Some commands do not use the checked register rows:

- **Renumber** — openings are picked interactively in Revit
- **Door Heights** — uses its own project-door workflow
- **Curtain Wall Views** — curtain walls are picked interactively in Revit
- **Conform Views** — works on the active opening view or all opening views
- **Dimension Window Views** — works on the active Window view or all standard Window views
- **Place on Sheet** — uses the Window or Door placement workflow

!!! tip "Check the scope before applying changes"

    The Opening Register is useful for reviewing the project, but a checked selection only affects commands that explicitly use register scope.

---

## Mixed Opening Categories

Some commands can process Windows, Doors and Curtain Walls together. Others require one category.

**Tag**, for example, requires the selected scope to contain a single opening category because Windows, Doors and Curtain Walls use different Revit tag categories and types.

If a tagging scope contains mixed opening categories, Flow stops the operation and asks you to select only one category.

Filter or check one category before running **Tag**.

---

## Selection and Model Changes

Normal register navigation does not change the opening itself.

Activities such as:

- searching
- filtering
- highlighting a row
- checking rows
- selecting from the model
- focusing an opening

are used to review, locate or define scope.

Model changes occur only when you run a modifying workflow such as **Standardise**, **Tag**, **Generate Views** or another Openings Manager operation that explicitly changes project data.

!!! note

    **Refresh** is an exception to a simple "navigation versus command" distinction. Refresh rebuilds the register, but it also applies the **Zero Window Sill Height** Global Parameter rule before the audit is rerun.

---

## Related Help

- [**Openings Manager**](index.md)
- [**Reviewing Openings**](reviewing-openings.md)
- [**Standardising Openings**](standardising-openings.md)
- [**Guided Renumbering**](guided-renumbering.md)
- [**Tagging Openings**](tagging-openings.md)
