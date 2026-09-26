# SRT Altium Library V1

Please download from the following link:
https://drive.google.com/file/d/1UaClluEFgvl3Y480iEcFnPhlo8__sSfv/view?usp=sharing

Install the intlib to your Altium. All design blocks are made using this library.

# Altium Designer Snippets

This repository contains reusable schematic and PCB snippets for Altium Designer. Follow the instructions below to install or update these snippets on your local machine.

---

## Installation Guide

### Step 1: Clone or Download the Repository
If you haven't already, clone or download this repository to your local computer:
```bash
git clone <REPOSITORY_URL>
```
*(Or download and extract the repository ZIP file).*

---

### Step 2: Open the Local Altium Snippets Folder
You can jump directly to Altium's default snippets directory using Windows Run:

1. Press <kbd>Win</kbd> + <kbd>R</kbd> to open the **Run** dialog.
2. Paste the following command and press **Enter**:
   ```cmd
   explorer "%PUBLIC%\Documents\Altium\AD25\Examples\Snippets Examples"
   ```
   > **Note:** If you are using a different version of Altium (e.g., AD24 or AD26), replace `AD25` in the path with your installed version.

---

### Step 3: Replace with Repository Folder Contents
1. *(Recommended)* Make a backup copy of your existing `Snippets Examples` folder if you have custom snippets saved there.
2. Locate the `Snippets Examples` folder inside this Git repository.
3. Copy all files and folders inside the repository's `Snippets Examples` directory.
4. Paste them into the local Altium directory you opened in **Step 2**, selecting **Replace the files in the destination** when prompted.

---

### Step 4: Verify in Altium Designer
1. Launch or switch to **Altium Designer**.
2. Open any schematic (`.SchDoc`) or PCB document (`.PcbDoc`).
3. In the bottom-right corner, click **Panels** > **Snippets** (or go to **View** > **Panels** > **Snippets**).
4. The newly installed snippet folders and files should now appear in the list and be ready for drag-and-drop placement.
