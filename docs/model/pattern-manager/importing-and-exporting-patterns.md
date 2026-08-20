# Importing and Exporting Patterns

Pattern Manager reads approved PAT content from the shared library and can export individual library or project patterns as PAT files.

---

## Load External Pattern Content

Pattern Manager does not use a separate **Import** command or a one-off file picker.

External PAT content is made available through the configured shared pattern library:

1. Add the PAT file to the appropriate library folder.
2. Open Pattern Manager, or click **Refresh** if it is already open.
3. Find and select the required pattern definition.
4. Click **Load**.

This keeps externally sourced patterns visible and reusable through the managed library rather than importing from unrelated local locations.

---

## Supported PAT Content

Pattern Manager reads `.pat` files recursively from the configured library.

The parser recognises:

- multiple pattern definitions in one PAT file;
- `%UNITS=MM` and `%UNITS=INCH` unit declarations;
- model and drafting target declarations;
- optional descriptions; and
- PAT grid lines containing angles, origins, offsets, shifts and dash data.

Patterns with missing targets, no grid definitions or malformed grid data are reported through library warnings.

!!! note "PAT definitions need Flow metadata"

    A usable definition needs recognised units, a model or drafting target and at least one valid grid. Correct the source PAT file if Flow reports unknown or incomplete information.

---

## Export a Library Pattern

1. Open the **Pattern Library** tab.
2. Select the required pattern.
3. Click **Export**.
4. Choose the filename and destination.

Flow exports only the selected pattern, even when its source PAT file contains several definitions.

---

## Export a Project Pattern

1. Open **Project Patterns**.
2. Select or right-click the required pattern.
3. Choose **Export**.
4. Choose the filename and destination.

The default filename uses the selected pattern name with a `.pat` extension. Flow removes a leading `*` before creating the filename.

The name must not contain characters that Windows does not allow in a filename.

---

## Exported PAT Structure

Flow writes:

- the pattern units;
- the pattern name;
- the description when one is available;
- the model or drafting target; and
- every grid definition and dash sequence.

The file is written as UTF-8 without a byte-order mark and uses high numeric precision to reduce changes to the pattern geometry during export.

If the destination file already exists, the save dialog asks before overwriting it.

---

## Related Help

- [Pattern Manager](index.md)
- [Browsing the Pattern Library](browsing-pattern-library.md)
- [Project Patterns](project-patterns.md)
- [Creating and Editing Patterns](creating-and-editing-patterns.md)
- [Troubleshooting](troubleshooting.md)