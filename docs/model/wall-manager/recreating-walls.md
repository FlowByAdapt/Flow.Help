# Recreating Original Walls

Wall Manager can replace generated separated walls with the compound walls recorded during the original separation operation.

This workflow is useful when the separated construction layers are no longer required or the wall needs to return to its original compound-wall condition.

---

## Select Generated Walls

Select one or more walls created by Wall Manager, then open the tool.

You do not need to select every generated layer manually. Wall Manager uses the recorded separation identity to find the related generated walls.

Multiple original walls can be recreated in one operation, including walls from different recorded separation groups.

!!! tip "One generated wall is enough"

    Select a generated wall from each original wall you want to restore. Wall Manager uses its recorded separation identity to locate the related generated layers.

---

## Run Recreation

1. Review the selected generated wall sets.
2. Check any integrity warnings.
3. Choose **Recreate original**.
4. Confirm the operation when prompted.
5. Review the restored walls and hosted elements in Revit.

Wall Manager recreates the recorded compound wall, restores supported constraints and orientation, and restores or rehosts supported doors and windows.

Compatible wall joins are healed where possible.

---

## Integrity Checks

Before recreation, Wall Manager checks that the generated wall set can be safely related to its recorded original.

Ordinary join changes caused by neighboring walls being recreated do not by themselves prevent recreation. The check focuses on whether the required generated walls and their recorded relationship remain suitable for restoration.

Recreation may be blocked when generated walls have been deleted, substantially changed, or can no longer be matched safely to the recorded operation.

This prevents Wall Manager from silently discarding later modelling work.

!!! warning "Do not bypass an integrity warning"

    A blocked recreation usually means a generated wall is missing or has been materially changed. Review the affected set before deciding how to restore it.

---

## Recreating Adjacent Walls

Adjacent separated walls can be recreated together or in successive operations.

When one original wall is recreated first, the resulting join changes should not prevent the neighboring recorded wall from being recreated. Review the final intersections after the batch is complete because Revit may resolve join order differently as walls are restored.

---

## Hosted Doors and Windows

Supported hosted elements are returned to the recreated compound wall with their supported instance information and global parameter associations.

Review the restored opening after recreation, particularly where the surrounding geometry or wall joins have changed since separation.
