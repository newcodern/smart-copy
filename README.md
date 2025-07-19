# Smart Copy

Smart Copy is a Windows desktop application that lets you copy the contents of a folder to another destination smartly — with overwrite protection, backup, and full restore capabilities. The application is designed for non-technical users who want simple but powerful file syncing and backup with a GUI.

## Features

- 🧠 Smart Copy:
  - Automatically copies new files.
  - Prompts user before overwriting existing files.
  - Creates backup before overwriting anything.

- ♻️ Restore:
  - Restore files from any previous copy session.
  - Deletes newly added files.
  - Restores all overwritten files to their original state.

- 📁 Drag & Drop support for folders.
- 📝 Log viewer with real-time updates.
- 💾 Automatic backup with timestamped folders.

---

## Usage (EXE Version)

1. **Run the App**  
   Double-click the `SmartCopy.exe` file. No installation required.

2. **Select Folders**
   - Set the **Source Folder** (folder you want to copy from).
   - Set the **Destination Folder** (folder you want to copy to).
   - You can use **Browse** or drag and drop the folder paths into the fields.

3. **Smart Copy**
   - Click the 🔁 **Smart Copy** button.
   - The app will ask before overwriting files.
   - It will backup any overwritten file and log newly added ones.

4. **Restore**
   - Choose a restore point from the dropdown (created automatically during Smart Copy).
   - Click ♻️ **Restore** to revert all changes: 
     - Restores overwritten files.
     - Deletes added files from that session.

5. **Clear Log**
   - Click 🧹 **Clear Log** to clear the output log window.

---

## Backup Folder Structure

Backups are stored in a folder named `backup_restore/` in the same directory as the executable. Each session creates a timestamped subfolder containing:
- `overwritten/` — stores original files before they were overwritten.
- `added.log` — tracks new files that were added during the copy process.

---

## Notes

- The app includes a built-in watermark and protection check. Tampering will close the app.
- Designed for Windows only (tested on Windows 10/11).
- Works as a portable executable (`.exe`), no installation needed.

---

## License
Made for personal or internal use.
