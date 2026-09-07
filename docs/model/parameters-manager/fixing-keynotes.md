# Fixing Keynotes

Use **Fix Keynotes** to start a batch keynote-standards operation for supported Revit files beneath a selected folder.

The workflow discovers the files, creates a batch job and starts Flow's separate BatchRunner. Output is directed to a **NewFiles** folder so the selected source location is not used as the output location.

**Ribbon:** Flow → Content → Parameters Manager

---

## Before You Start

Check that:

- The selected folder contains the Revit files you intend to process
- You have access to the folder and its subfolders
- The applicable Flow keynote configuration is installed
- Flow's BatchRunner is available with the current installation
- There is sufficient space for processed output copies

Close or save source files where practical before starting a batch operation.

!!! warning "Review the complete folder tree"

	Fix Keynotes searches the selected folder and all of its subfolders. Check the complete folder tree before starting the workflow.

---

## Start Fix Keynotes

1. Open **Parameters Manager**.
2. Expand **Maintenance**.
3. Select **Fix Keynotes**.
4. In **Select folder containing Revit files to process**, choose the source folder.
5. Confirm the folder selection.
6. Review the startup message, including the number of files found and the output location.

After the folder is accepted, Flow prepares the batch and attempts to launch it immediately. There is no separate file checklist or second confirmation.

<!-- SCREENSHOT: Folder picker titled Select folder containing Revit files to process, with a representative source folder selected. -->

---

## Files Included

The recursive scan includes:

- Revit family files (`.rfa`)
- Revit project files (`.rvt`)
- Revit template files (`.rte`)

Extension matching is case-insensitive.

If no supported files are found, Flow reports:

> No Revit family, project, or template files were found.

No batch process is started.

---

## Files Excluded Automatically

Flow excludes:

- Files already inside a folder named `NewFiles`
- Numbered Revit backup files such as `Project.0001.rvt`
- Files whose extensions are not `.rfa`, `.rvt` or `.rte`

This prevents existing batch output and standard numbered Revit backups from being added to the new job.

!!! note "Other folders are included"

	The scan does not provide a general excluded-folder list. Supported Revit files in other subfolders beneath the selected source are included.

---

## What Flow Creates

After finding supported files, Flow:

1. Creates a `NewFiles` folder directly beneath the selected source folder.
2. Creates a timestamped keynote-standards job identifier.
3. Creates a local run folder for the job.
4. Writes a JSON job file containing the source files and processing settings.
5. Records a result-file path for the batch run.
6. Resolves the installed `KeynoteStandards.json` configuration.
7. Attempts to start `Flow.Revit.BatchRunner.exe`.

The job uses the current Revit application year. If the Revit version cannot be parsed, the launcher falls back to 2027 for the job definition.

---

## Startup Message

When the BatchRunner starts, Parameters Manager reports:

- Selected folder
- Number of files found
- Local run folder
- `NewFiles` output folder

<!-- SCREENSHOT: Keynote Standards Started message showing selected folder, file count, run folder and output folder. -->

!!! important "Started does not mean completed"

	This message confirms that the external BatchRunner process was started. It does not confirm that every Revit file was opened, changed and saved successfully.

	Review the batch result information and processed output before relying on the files.

---

## Output

The batch job is configured with:

- The selected folder as its source root
- `NewFiles` as its output root
- The installed keynote standards configuration
- Removal of output backup files enabled

Review the generated copies before replacing, issuing or distributing source content.

<!-- SCREENSHOT: File Explorer showing the selected source folder and the generated NewFiles output folder after a completed run. -->

---

## If BatchRunner Is Missing

If Flow cannot find the BatchRunner executable, it reports:

- That `BatchRunner.exe` was not found
- The expected executable path
- The job-file path that was created

The `NewFiles` and run folders may already have been created before this check occurs, but no external batch process is started.

Contact the Flow administrator or repair the Flow installation rather than manually editing the generated job file unless you are responsible for maintaining the batch system.

---

## Cancel the Workflow

Cancel or close the folder picker before selecting a source folder.

Flow reports that Keynote Standards was cancelled and does not collect files or start the BatchRunner.

After the folder has been accepted and the external process has started, closing Parameters Manager does not constitute a verified cancellation of that batch process.

---

## Expected Result

At the launcher stage, a successful result means:

- Supported source files were discovered
- A batch job was created
- A `NewFiles` output location was prepared
- The external BatchRunner was started

Final success must be determined from the batch result and output files, not from the Parameters Manager startup message alone.

---

## If the Output Is Incomplete

Check:

1. The startup message's **Files found** count.
2. Whether the intended files use `.rfa`, `.rvt` or `.rte`.
3. Whether files were excluded as numbered backups or existing `NewFiles` content.
4. Whether the BatchRunner executable was found.
5. Whether the installed keynote configuration exists and is valid.
6. The batch result information for per-file failures.
7. The generated output before rerunning the operation.

---

## Current Limitations

- Folder scanning is recursive.
- Individual discovered files cannot be selected or excluded in the launcher.
- Only `.rfa`, `.rvt` and `.rte` files are supported.
- The Parameters Manager message confirms startup rather than final completion.
- Parameters Manager does not display live per-file progress in the reviewed launcher.
- Closing Parameters Manager is not a batch-cancellation command.
- Final file-level behaviour depends on the separate BatchRunner and installed keynote configuration.

---

## Related Help

- [Parameters Manager](index.md)
- [Parameters Manager Troubleshooting](troubleshooting.md)
