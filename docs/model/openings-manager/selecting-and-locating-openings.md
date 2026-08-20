# Selecting and Locating Openings

The Openings Manager register is connected to the active Revit model.

Use the selection and navigation controls to move between the register and the model without having to locate each opening manually.

---

## Select an Opening from the Register

Select a row in the Openings Manager register.

The corresponding Revit element is selected in the model.

This provides a quick way to identify the physical opening represented by a register row.

---

## Zoom to an Opening

Double-click an opening in the register to locate it in Revit.

Flow zooms to the corresponding element so that it can be reviewed in context.

!!! tip "Use double-click when reviewing issues"

    If an opening shows an unexpected mark, Global Parameter status or other issue, double-click the row to inspect the element directly in the model.

---

## Select Openings from the Model

Use **Select from Model** when it is easier to identify the required openings graphically in Revit.

1. Click **Select from Model**.
2. Select the required openings in Revit.
3. Finish the Revit selection.
4. Return to Openings Manager.

The selected openings are identified in the register.

Flow temporarily highlights model-picked records so they are easier to locate.

---

## Select Filtered Openings

Use the register filters to isolate the required openings, then use **Select Filtered** to select that group.

For example:

1. Set **Category** to Windows.
2. Set the required **Level**.
3. Set **Phase** to New.
4. Apply any additional search or status filters.
5. Click **Select Filtered**.

This is useful when a command needs to be applied to a defined group rather than the whole project.

---

## Clear the Current Selection

Use **Clear** to remove the current Openings Manager selection.

This is useful before building a new selection or changing the working scope.

---

## Focus the Current Selection

Use **Focus** to locate the current selected opening or openings in Revit.

Focus is useful when you have built the selection from the register and want to inspect those elements in the model before running another command.

---

## Checked Openings and Command Scope

Several Openings Manager commands allow you to choose which openings the command should affect.

Depending on the current register state, the available scope can include:

- checked openings
- filtered openings
- all openings

This allows you to build a working set in the register before running the command.

!!! info "Scope is command-specific"

    Not every Openings Manager tool uses the same scope options.

    Some workflows, such as Guided Renumber, use their own interactive Revit selection process instead.

---

## Mixed Opening Categories

Some commands can work with windows, doors and curtain walls together.

Others require a particular category.

For example, tagging uses category-specific Revit tag types. A mixed Window/Door/Curtain Wall selection cannot be tagged as one operation.

If required, filter or select one opening category before running the command.

---

## Selection Does Not Change the Model

Selecting, filtering or focusing openings does not modify the opening itself.

Changes are only made when you run a command such as:

- Standardise
- Door Heights
- Tag
- Generate Views
- a Global Parameter operation

This makes the register safe to use for reviewing and organising the project before applying changes.

---

## Related Help

- [**Reviewing Openings**](reviewing-openings.md)
- [**Standardising Openings**](standardising-openings.md)
- [**Guided Renumbering**](guided-renumbering.md)
- [**Tagging Openings**](tagging-openings.md)