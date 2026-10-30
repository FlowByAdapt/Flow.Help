# Restoring Previous Tools

Use **Restore previous tools** when you need to return a selected Revit year to a compatible previous Flow tools installation retained by the installer.

---

## Before You Start

Confirm that:

- all Revit sessions are closed
- the correct Revit year is selected
- a compatible restore backup is available
- you have reviewed the release and backup identified in the confirmation

!!! note "A restore backup must exist"

    Detecting installed tools does not guarantee that a compatible previous installation has been retained. Workstation Manager reports when no suitable restore backup is available.

---

## Restoring Tools

1. Open **This computer**.
2. Select the required Revit year.
3. Select **Restore previous tools**.
4. Review the release and backup shown in the confirmation.
5. Confirm the restore, or cancel to keep the current installation.
6. Wait for the result and review the refreshed release information.
7. Open that Revit version and check that Flow loads correctly.

Selecting the restore button opens a confirmation first. Confirming the action performs the restore for the selected year.

!!! warning "Restore changes the selected tools installation"

    Restoring replaces the active Flow tools configuration for the selected Revit year with the retained previous configuration. Other Revit years remain as they are.

<!-- Screenshot recommended:
Show the Flow-styled restore confirmation with the Revit year and backup details.
Use a fictional Windows user and path.
-->

---

## Returning to the Approved Release

1. Close all Revit sessions again.
2. Select **Check updates**.
3. Select the restored Revit year.
4. Select **Install / update tools**.
5. Complete the installation and review the result.

An update may be offered again after a restore when the restored tools are older than the approved release. This is expected.

---

## Related Help

- [Installing and Updating Revit Tools](installing-and-updating-tools.md)
- [Troubleshooting](troubleshooting.md)
