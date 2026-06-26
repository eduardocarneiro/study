
 How terminal rendering works with WSL?
 
 Ubuntu is running inside Windows Subsystem for Linux, **your Linux environment isn't the one rendering the text—your Windows terminal emulator is.**

To fix those broken icons in your tmux status bar, you need to install and configure a **Nerd Font** on your **Windows host machine**, not inside Ubuntu.

Here is how to get it working in a few quick steps:

### Step 1: Download a Nerd Font on Windows

You need a font that includes all the special developer icons (like Nerdfonts or Powerline symbols).

1. Go to the official [Nerd Fonts Downloads](https://www.nerdfonts.com/font-downloads) page on your Windows browser.

2. Download a popular, clean font like **FiraCode Nerd Font**, **Hack Nerd Font**, or **Meslo Nerd Font**.

3. Extract the downloaded `.zip` file.

4. Highlight the `.ttf` (or `.otf`) files, right-click, and select **Install** (or _Install for all users_).

### Step 2: Apply the font to your PowerShell window

Look at your window's title bar to see which method applies to you:

#### Method A: If you are using Windows Terminal (Tabs at the top)

If your PowerShell window has a tab bar at the very top, it's running inside Windows Terminal:

1. Press `Ctrl + ,` (or click the down arrow in the tab bar and select **Settings**).

2. In the left sidebar, click on **PowerShell** (or **Defaults** to fix it everywhere).

3. Click on **Appearance**.

4. Change **Font face** to your newly installed font (e.g., `CaskaydiaCove NF` or `FiraCode NF`).

5. Click **Save**.

#### Method B: If you are using the Classic PowerShell Window (No tabs)

If it's the older, solid-colored window frame:

1. Right-click the **Title Bar** at the very top of the window.

2. Select **Properties**.

3. Go to the **Font** tab.

4. Select your installed Nerd Font from the list (Note: Classic Windows Console is picky and sometimes only shows fonts explicitly configured for it, like _Cascadia Code_ or _Meslo_).

5. Click **OK**.

### Step 3: Refresh your session

type `ctrl` + `b` + `r`  to reload the tmux configuration if you already copied the `.tmux.conf` 

If not close and open tmux again.