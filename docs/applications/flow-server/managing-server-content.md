# Managing Server Content

The **Browse** tab provides administrative commands for organising Revit Server folders and controlling access to models.

These commands are available from the right-click menu when the selected item and Revit Server version support the operation.

---

## Creating a Folder

1. Select the parent folder in **Browse**.
2. Right-click and select **Create Folder**.
3. Enter the new folder name.
4. Review the parent folder and select **Create**.

Flow creates the folder and refreshes the server tree.

---

## Renaming a Folder

1. Select the folder.
2. Right-click and select **Rename Folder**.
3. Enter the new name.
4. Review the change and select **Rename**.

Protected server folders cannot be renamed. After a successful rename, Flow reloads the tree and restores the expanded branches using the new path where possible.

---

## Moving a Folder

1. Select the folder.
2. Right-click and select **Move Folder**.
3. Select a valid destination folder.
4. Review the source and destination.
5. Select **Move**.

Flow excludes invalid destinations, including the current parent and locations within the selected folder itself. The move is blocked if a folder with the same name already exists at the destination or the source no longer exists.

Protected server folders cannot be moved.

---

## Locking a Model

1. Select an available model.
2. Right-click and select **Lock Model**.
3. Review the model name and RSN path.
4. Select **Lock**.

The model becomes unavailable to users until it is unlocked. Flow refreshes the server tree and displays a lock indicator beside the model.

---

## Unlocking a Model

1. Select an administratively locked model.
2. Right-click and select **Unlock Model**.
3. Review the model name and RSN path.
4. Select **Unlock**.

The model becomes available to users again and Flow refreshes the server tree.

---

## Deleting a Model

1. Confirm that the required model archive has completed and can be opened from its archive location.
2. Select the model in **Browse**.
3. Right-click and select **Delete Model**.
4. Review the model and its location.
5. Select **Delete Model**.

Flow deletes the model and reloads the parent folder.

!!! warning "Model deletion cannot be undone"

    Deleting a model is separate from archiving. Flow does not create or verify an archive as part of the deletion command.

---

## Deleting an Empty Folder

1. Select the empty folder.
2. Right-click and select **Delete Folder**.
3. Review the location.
4. Select **Delete Folder**.

Protected server folders cannot be deleted.

---

## Deleting a Folder and Its Contents

1. Confirm that every required model beneath the folder has been archived and verified.
2. Select the folder.
3. Right-click and select **Delete Folder**.
4. Review the reported number of models and subfolders.
5. Select **Continue**.
6. Review the final confirmation.
7. Select **Permanently Delete**.

Flow permanently removes the selected folder, its models and all subfolders.

!!! warning "Two confirmations are required"

    A non-empty folder requires an initial confirmation followed by a final permanent-deletion confirmation.

    The folder and everything beneath it are removed from Revit Server and cannot be recovered by Flow Server.

<!-- Screenshot recommended:
Show the first delete-folder confirmation for a fictional non-empty project.
Include the model and subfolder counts but no real project information.
-->

---

## Related Help

- [Flow Server](index.md)
- [Connecting and Browsing](connecting-and-browsing.md)
- [Archiving Projects](archiving-projects.md)
- [Troubleshooting](troubleshooting.md)