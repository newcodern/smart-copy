## 🛠 How to Use Smart Copy (Step-by-Step Guide)

### 🖥 1. Launch the Application

* Open `smart_copy_0.9.1.exe`.
* No installation is needed. The app runs as a portable standalone executable.

---

### 📁 2. Select Source & Destination Folders

* **Source Folder**: the folder you want to copy files **from**.
* **Destination Folder**: the folder where files will be copied **to**.

🧲 You can:

* Click the **"Browse"** button to choose folders.
* OR drag and drop folders into the input fields.

---

### 🔁 3. Smart Copy (Main Feature)

Click **🔁 Smart Copy** to begin copying.

#### What Happens:

1. New files in source → copied to destination ✅
2. If a file with the same name exists in destination:

   * You’ll be **asked** if you want to overwrite it.
   * If yes:

     * The existing file is **backed up** first.
     * Then it's replaced with the new one.
   * If no:

     * It will be skipped.

🗂 Backup is created in `backup_restore/` folder with a **timestamp**.

🧾 All added and overwritten files are logged.

* Overwritten files → stored in `overwritten/`
* Newly added files → listed in `added.log`

---

### ♻️ 4. Restore From Backup

#### Why use Restore?

If something went wrong after Smart Copy, you can undo everything.

#### How to restore:

1. Select the same **Destination Folder** you used earlier.
2. Choose a **Restore Point** from the dropdown (based on timestamp).
3. Click **♻️ Restore**.

#### What Happens:

* Files from `overwritten/` are restored.
* Files listed in `added.log` are deleted.

✅ All changes are rolled back.

---

### 📖 5. Log Viewer

* All activities (copy, skip, error, restore) are displayed in the bottom log window.
* Click 🧹 **Clear Log** to reset the log view.

---

## 💡 Real-World Scenarios

### 📌 Scenario 1: Updating a USB Drive Safely

* You want to update your USB backup folder without losing important files.
* Use Smart Copy to sync your latest work folder to the USB drive.
* If any file on USB already exists, Smart Copy will ask before replacing it — and will back it up first!

---

### 📌 Scenario 2: Backup and Restore While Working With Projects

* You maintain a large project and frequently update assets.
* Before copying updated files, Smart Copy creates a backup of what's about to be replaced.
* If your update breaks something, just use the Restore function to get the old files back!

---

### 📌 Scenario 3: Avoiding Accidental Data Loss

* You're syncing folders between drives (e.g. HDD → SSD).
* If you accidentally overwrite something, you can recover it from the restore point without needing a separate backup system.

---

## 📦 Where Are Backups Stored?

Backups are stored in the app's directory inside the folder:

```
backup_restore/
  └── 17 July 2025 20-30-12/         <-- Timestamped session
        ├── overwritten/             <-- Original files that got replaced
        └── added.log                <-- List of files added to destination
```

You can delete old backup folders manually if you don’t need them anymore.

---

## 🚫 Things to Keep in Mind

* Make sure you have **read permission** on the source and **write permission** on the destination.
* This tool does **not merge files** — it copies them exactly as they are.
* Do not rename or modify files inside `backup_restore/` unless you know what you're doing.
* The app checks for tampering — if the watermark is changed or removed, it will automatically close.
