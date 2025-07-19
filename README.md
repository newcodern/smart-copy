## 🧠 Understanding How Smart Copy Works

Smart Copy is **not just a file copier**. It’s a **safe folder syncing tool** with built-in **backup and restore** logic.

---

## 📁 Folder Definitions

| Field                  | Meaning & Purpose                                                                                                        |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **Source Folder**      | The folder **you want to copy from**. It contains the files you want to move or update.                                  |
| **Destination Folder** | The folder **you want to paste into**. It's the target location (e.g., USB drive, external HDD, project directory, etc.) |
| **Restore Point**      | A backup session saved from a previous Smart Copy. You can use it to undo changes.                                       |

---

## 🔁 Smart Copy Logic (Behind the Scenes)

1. **You choose the source and destination folders.**

2. **App walks through the source folder** and checks each file:

   * If the file **does not exist** in destination → it gets **added** ✅
   * If the file **already exists** in destination:

     * You are asked: "Do you want to overwrite?"
     * If you choose **Yes**:

       * The destination file is **backed up** first.
       * Then it is **replaced** by the source file.
     * If you choose **No**:

       * The file is **skipped**.

3. The app logs everything:

   * \[ + ] = New file added
   * \[ # ] = File overwritten (but backup saved)
   * \[ ! ] = File skipped (you chose not to overwrite)
   * \[ ERROR ] = Something went wrong

4. The progress bar tracks how many files have been processed.

---

## 💾 What Happens to Overwritten or New Files?

All changes are stored in a backup folder under `backup_restore/`:

```
backup_restore/
└── 19 July 2025 18-24-09/        <-- Timestamp
     ├── overwritten/            <-- Original versions of files you chose to overwrite
     └── added.log               <-- List of newly added files in destination
```

You can restore from this session later using the **Restore** button.

---

## ♻️ Restore Flow (Undo Copy Session)

1. You select the same **Destination Folder**.
2. Pick a **Restore Point** from the dropdown.
3. Click **Restore**.

Then Smart Copy:

* Restores any files in `overwritten/` to their original path.
* Deletes any files listed in `added.log`.

It will **revert the destination folder back** to how it was before you ran Smart Copy that time.

---

## 🎯 Example Use Case (Simple Scenario)

> You want to sync your "Projects" folder to your external hard drive (E:\Backup)

1. **Source Folder**: `C:\Users\You\Documents\Projects`
2. **Destination Folder**: `E:\Backup`
3. Click 🔁 **Smart Copy**

   * It will:

     * Copy all new files from `Projects` to `E:\Backup`
     * Ask before overwriting anything
     * Save backups of overwritten files
4. If later you regret copying, or something breaks:

   * Choose the same `E:\Backup`
   * Select the correct restore point
   * Click ♻️ **Restore**
   * Done, everything is rolled back!

---

## ⚠️ Best Practices

* **Do not use this tool to move files between folders with live system data** (e.g., system32, program files).
* Always review which folders you are working with.
* After a copy session, you can keep or delete the backup folder (`backup_restore`) if you no longer need it.
