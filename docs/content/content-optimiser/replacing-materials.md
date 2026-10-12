# Replacing Materials

Use **Materials** to map supported family material assignments to approved materials from the active project.

---

## Before Mapping

Activate the project containing your approved materials before auditing. The same project must be available when applying the material plan.

The **Family materials** list shows the source materials. **Project replacements** shows the available project materials. Search either list by name or keynote.

---

## Propose a Replacement

1. Select a source in **Family materials**.
2. Review its details and **Defaults** and **Direct** counts.
3. Select the approved material in **Project replacements**.
4. Review its details.
5. Choose **Propose Replacement**.
6. Check the mapping list and its **Status**.

Use **Remove Mapping** to remove a selected proposal or **Clear Plan** to clear the material mapping plan.

!!! tip "Compare definitions as well as names"

    Check the intended finish, appearance and keynote. Similar names alone do not establish that two materials are equivalent.

<!-- SCREENSHOT: Materials tab with the family and project lists, selected material details, Defaults/Direct counts and a proposed mapping. -->

---

## Understand Mapping Coverage

Supported writes include editable material parameter defaults and supported direct host assignments. Protected or formula-driven defaults remain restricted. Parameter associations remain intact and can follow their changed material defaults.

The **Defaults** count represents parameter/type assignments rather than a count of visible geometry pieces. Read the details and report for coverage and retained uses.

!!! note "Some source materials remain"

    Nested and imported internals remain unchanged. Mapping does not prove that the original material is unused or automatically delete it. Review eligible unused source materials separately on **Purge**.

The current workflow blocks a target whose name already exists on a family material. Choose a different approved target or resolve the family material definitions separately and audit again.

---

## Advanced Material Options

Expand **Advanced material options** when additional checks are required.

- **Test Project Material** tests transfer using a disposable family copy.
- **Test Load-back** supports checking the result in a disposable test project.
- **Import differing thermal asset with unique name** allows differing thermal definitions to remain distinct where supported.

Review any transfer or asset-collision message before proceeding. Use a disposable project for load-back testing.

---

## Check the Output

After saving, place and inspect the relevant types in a test project. Check visible finishes, parameter-driven assignments, retained nested content and material definitions. A transfer check does not establish rendered equivalence for every family.

---

## Related Help

- [**Selecting and Auditing Families**](selecting-and-auditing.md)
- [**Purging Unused Content**](purging-unused-content.md)
- [**Reviewing and Saving**](reviewing-and-saving.md)
- [**Troubleshooting**](troubleshooting.md)
