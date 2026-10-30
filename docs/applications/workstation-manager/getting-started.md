# Getting Started with Workstation Manager

Flow Workstation Manager is installed for the Windows account that uses the computer.

---

## Before You Start

You need:

- a 64-bit Windows computer
- the approved Workstation Manager installation package
- access to your office's shared Flow folder
- permission to read approved releases and save computer reports

Your office administrator supplies the shared folder location. Use the same location as the other office computers.

!!! note "The shared Flow folder is not a Revit Server address"

    **NAS folder** points to the office folder containing Flow releases, standards and inventory reports. It is separate from the Revit Server connection used by Flow Server.

---

## Installing Workstation Manager

1. Sign in using your normal Windows account.
2. Copy the supplied installation ZIP to your computer.
3. Choose **Extract All**.
4. Open the extracted folder and run **Install.cmd**.
5. Open **Flow Workstation Manager** from **Start → Flow by Adapt**.

The package includes its required runtime. A separate Visual Studio installation is not needed.

!!! tip "Extract the package first"

    Run the installer from the extracted folder rather than from inside the ZIP.

---

## Connecting to the Office Folder

1. Review the **NAS folder** shown at the top of the window.
2. If necessary, enter the location supplied by your office administrator.
3. Select **Save folder**.
4. Review the status message.

Workstation Manager remembers the folder for your Windows account.

---

## Checking In This Computer

Workstation Manager automatically scans and attempts to check in when opened, including after updating itself. A check-in saves the computer report to the office folder.

To repeat the process manually:

1. Open **This computer**.
2. Select **Scan and check in**.
3. Review the detected Revit versions and Flow tools releases.
4. Confirm that the status reports successful delivery to the office folder.

Open **Office computers** to review the received report.

!!! info "Reports are saved locally first"

    If the office folder is unavailable, Workstation Manager keeps the local report. The normal scheduled checks can deliver a fresh report when the connection is available again.

<!-- Screenshot recommended:
Show This computer after a successful check-in, including NAS folder, action buttons
and representative Revit rows. Use a fictional network address and computer name.
-->

---

## Understanding the Versions

| Version | What it identifies |
|---|---|
| **Installed version** on This computer | The installed Autodesk Revit version. |
| **Revit tools release** | The installed Flow tools package for that Revit year. |
| **Workstation** | The Flow Workstation Manager application version. |
| **Server version** | The Flow Server application version. |

These products have independent version numbers. They do not need to match each other.

---

## Related Help

- [Flow Workstation Manager](index.md)
- [Installing and Updating Revit Tools](installing-and-updating-tools.md)
- [Background Checks and Update Notices](background-checks-and-notices.md)
- [Troubleshooting](troubleshooting.md)
