# Installing and Updating Flow Apps

The **Flow apps** tab compares the installed versions of Workstation Manager and Flow Server with office-approved application releases.

---

## Checking Application Updates

1. Open **Flow apps**.
2. Select **Check app updates**.
3. Review **Installed version**, **Approved version** and **Update status**.

| Status | Meaning |
|---|---|
| **Up to date** | The installed version matches the approved version. |
| **Update available** | A newer approved version is available. |
| **Install available** | The application is missing and an approved installer is available. |
| **No approved app release set** | No approved application package has been configured. |
| **Installed version needs review** | Workstation Manager cannot confidently compare the detected installation with the approved release. |

**Open update folder** opens the approved package location when an installation or update is available for the selected application. **Preview app notice** shows an example Workstation Manager update notice without starting an installation.

---

## Updating Workstation Manager

1. Select **Workstation Manager**.
2. Select **Install / update app**.
3. Allow Workstation Manager to download and verify the package, then close, update and reopen.
4. Review the result shown after reopening.

Settings and inventory are retained. The updater keeps an application backup and reports the outcome after restarting.

!!! note "Use the installed application"

    Self-update is intended for the standard installed copy of Workstation Manager. If you are running an extracted test copy, install the approved package using **Install.cmd** first.

---

## Installing or Updating Flow Server

1. Close Flow Server.
2. Open **Flow apps** and select **Check app updates**.
3. Select **Flow Server**.
4. Select **Install / update app**.
5. Complete the installer and any administrator prompt.
6. Review the refreshed application version.

The same action can install Flow Server when it is missing and an approved installer is available. Workstation Manager automatically scans and attempts to check in after a successful Server installation.

See [Getting Started with Flow Server](../flow-server/getting-started.md) for its installation requirements and worker components.

!!! info "Missing applications are optional installations"

    A missing optional application can show **Install available**, but it is not counted as an update in the red indicator or update reminders.

---

## Related Help

- [Flow Workstation Manager](index.md)
- [Background Checks and Update Notices](background-checks-and-notices.md)
- [Troubleshooting](troubleshooting.md)
- [Flow Server](../flow-server/index.md)
