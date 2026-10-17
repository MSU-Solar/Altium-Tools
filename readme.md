# SRT Altium Resources & Library Guide

All current Solar Racing Team (SRT) Altium resources are hosted in the following Google Drive folder:
* **[SRT Altium Google Drive Folder](https://drive.google.com/drive/folders/15iXzZmwW9jrID4Y5XLm886tc6TvLSeGV?usp=sharing)**

### Folder Contents Overview
* **`solar_lib_vX.intlib`**: The integrated component library. All design blocks and snippets are made using this library.
* **`snippets_vX.zip`**: Compressed archive containing reusable schematic and PCB snippets.
* **`JCL_Xoz_vX.RUL`**: Altium Design Rule files tailored for specific copper weights (e.g., 1oz, 2oz).
* **`archive/`**: Contains deprecated versions of libraries, snippets, and rules. 

> **Warning:** Do **not** use anything inside the `archive` folder for new designs. Always use the latest `_vX` files located in the root directory of the Drive folder.

---

## 1. Installing the Integrated Library & Design Rules

### Installing the Library
1. Download the latest `solar_lib_vX.intlib` from the Google Drive folder.
2. Drag the `.intlib` file directly over your **Altium Designer** window.
3. Click **Install** when prompted.

### Importing Design Rules (`.RUL`)
1. Download the appropriate `JCL_Xoz_vX.RUL` file for your board's copper weight from the Google Drive folder.
2. Open your `.PcbDoc` in Altium Designer and navigate to **Design** > **Rules**.
3. In the left-hand tree, right-click on **Design Rules** and select **Import Rules...**.
4. Press <kbd>Ctrl</kbd> + <kbd>A</kbd> to select all rule types and click **OK**.
5. Select your downloaded `.RUL` file, choose **Yes** to clear existing rules if prompted, and click **Apply** > **OK**.

---

## 2. Updating an Existing Project to a New Library Version

If you are migrating an existing project to a newer version of `solar_lib_vX.intlib`, use one of the two methods below to update your component links and push the latest symbols/footprints.

### Method 1: Using the Parameter Manager (Recommended)
1. Open any schematic document (`.SchDoc`) in your project.
2. Select **Tools** > **Parameter Manager** (Shortcut: <kbd>T</kbd>, <kbd>R</kbd>).
3. Under **Parameter Editor Options**, uncheck every box **except** for **Parts**.
4. Set **That Meet the Following Criteria** to **All Objects** and click **OK**.
5. Locate the **Library Name** column, right-click on any entry in that column, and select **Select Column**.
6. Hold <kbd>Ctrl</kbd> and click on any individual entries that you do **not** want to update to the new library to deselect them.
7. Right-click any selected cell and choose **Edit**.
8. Enter the exact filename of the new library (e.g., `solar_lib_vX.intlib`) and press **Enter**.
9. Click **Accept Changes (Create ECO)** in the bottom right.
10. Click **Validate Changes**, and if the ECO passes, click **Execute Changes**, then **Close**.
11. Proceed to **Finalizing the Update (Both Methods)** below.

### Method 2: Using Find Similar Objects
1. Close all open documents by right-clicking any document tab and choosing **Close All Documents**.
2. In the **Projects** panel, right-click your project's **Source Documents** folder and choose **Open All**.
3. Open any schematic file in your project containing parts to update.
4. Right-click a schematic symbol from the old library version and select **Find Similar Objects**.
5. In the filter parameters, set **Current Footprint** (or **Library**) to **Same** instead of **Any** (other filters can be left as **Any**).
6. At the bottom of the **Find Similar Objects** menu, change the scope dropdown from **Current Document** to **Open Documents**, ensure **Select Matching** is checked, and click **OK**.
7. With the old library components highlighted, press <kbd>Ctrl</kbd> + <kbd>A</kbd> to select all matching parts, open the **Properties** panel, and change the **Source** library to the new library. Repeat this step for each schematic page you want to update.
8. Proceed to **Finalizing the Update (Both Methods)** below.

### Finalizing the Update (Both Methods)
Once your component source names point to the new library via Method 1 or Method 2, push the physical updates from the library:
1. Select **Tools** > **Update from Libraries...** (Shortcut: <kbd>T</kbd>, <kbd>L</kbd>).
2. Under **Settings**, check **only** `Preserve parameter locations` and `Preserve parameter visibility`. Make sure all **Schematic Sheets** are selected.
3. Click **Next >** (Shortcut: <kbd>N</kbd>), then click **Finish**.
4. In the ECO menu, click **Validate Changes**, then **Execute Changes** once it passes.
5. Close the ECO menu. All components should now be up-to-date.

---

## 3. Altium Designer Snippets Installation Guide

Reusable schematic and PCB snippets are available for quick drag-and-drop placement. Follow the instructions below to install or update these snippets on your local machine.

### Step 1: Download the Snippets Archive
1. Navigate to the [SRT Altium Google Drive Folder](https://drive.google.com/drive/folders/15iXzZmwW9jrID4Y5XLm886tc6TvLSeGV?usp=sharing).
2. Download the latest `snippets_vX.zip` file from the main directory (or clone this repository if pulling via Git: `git clone <REPOSITORY_URL>`).
3. Extract the contents of `snippets_vX.zip` to a temporary folder on your computer.

---

### Step 2: Open the Local Altium Snippets Folder
You can jump directly to Altium's default snippets directory using Windows Run:

1. Press <kbd>Win</kbd> + <kbd>R</kbd> to open the **Run** dialog.
2. Paste the following command and press **Enter**:
   ```cmd
   explorer "%PUBLIC%\Documents\Altium\AD25\Examples\Snippets Examples"
   ```
   > **Note:** If you are using a different version of Altium (e.g., `AD24` or `AD26`), replace `AD25` in the path with your installed version.

---

### Step 3: Replace with Extracted Snippets Contents
1. *(Recommended)* Make a backup copy of your existing `Snippets Examples` folder if you have custom personal snippets saved there.
2. Open the extracted `snippets_vX` folder (or the `Snippets Examples` folder inside this Git repository).
3. Copy all files and folders inside the extracted directory.
4. Paste them into the local Altium `Snippets Examples` directory you opened in **Step 2**, selecting **Replace the files in the destination** when prompted.

---

### Step 4: Verify in Altium Designer
1. Launch or switch to **Altium Designer**.
2. Open any schematic (`.SchDoc`) or PCB document (`.PcbDoc`).
3. In the bottom-right corner, click **Panels** > **Snippets** (or go to **View** > **Panels** > **Snippets**).
4. The newly installed snippet folders and files should now appear in the list and be ready for drag-and-drop placement.
