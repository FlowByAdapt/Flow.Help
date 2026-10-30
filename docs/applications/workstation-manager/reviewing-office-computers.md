# Reviewing Office Computers

The **Office computers** tab displays the latest computer reports received through the shared office folder.

Each Revit installation has its own row. One computer may therefore appear several times.

---

## Refreshing Reports

1. Connect to the office network.
2. Open **Office computers**.
3. Review the latest reports.
4. Select **Refresh office reports** if you want to read them again immediately.

The view refreshes when selected and every minute while it remains visible and Workstation Manager is not busy.

!!! note "Reports show the latest check-in"

    Refreshing this view reads reports already received by the office folder. It does not remotely scan or install software on other computers.

    Check **Last checked** before treating a reported version as current.

---

## Understanding the Columns

| Column | What it shows |
|---|---|
| **Name / Computer** | The display name and reporting computer. |
| **Revit year / Revit version** | The Autodesk Revit installation reported by that computer. |
| **Last checked** | When the computer was scanned. |
| **Status** | Whether the reported Revit version matches the office standard. |
| **Revit tools release** | The detected Flow tools release and its approval comparison. |
| **Workstation** | The reported Workstation Manager version. |
| **Server version** | The reported Flow Server version. |

Reports older than seven days are marked old. **Not reported** indicates that the report does not provide that information; it is not proof that the application is missing.

!!! info "Revit standard and Flow release are separate checks"

    **Differs from standard** concerns the Autodesk Revit version. A computer can differ from the Revit standard while its Flow tools correctly show **Matches approved release**.

<!-- Screenshot recommended:
Show Office computers with fictional users and computers, one current report and
one older report. Keep the Revit standard and Flow release columns visible.
-->

---

## When a Version Looks Out of Date

Workstation Manager checks in automatically when opened and through scheduled checks. A computer that has been offline may not yet have delivered its latest report.

To request a fresh report immediately:

1. On the affected computer, connect to the office network and open Workstation Manager.
2. Select **Scan and check in** if a further check is needed.
3. Confirm successful report delivery.
4. Return to the reviewing computer and select **Refresh office reports**.

---

## Related Help

- [Getting Started](getting-started.md)
- [Background Checks and Update Notices](background-checks-and-notices.md)
- [Troubleshooting](troubleshooting.md)
