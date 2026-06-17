
# 🛠️ Tmux (Terminal Multiplexer)

Welcome to the Tmux workspace. This page serves as a central hub for navigating shortcuts, configurations, and deep dives into managing terminal spaces efficiently.

### Key Concepts & Architecture
Tmux organizes your workflow into a clean hierarchy of three levels:
* **Sessions:** High-level workspaces (e.g., one session for `Frontend`, one for `Backend`).
* **Windows:** Tabs within a session that occupy the full terminal view.
* **Panes:** Split screens inside a single window, allowing you to view processes side-by-side.

## ❓ What is TMUX?

**Tmux** (Terminal Multiplexer) is one of the most powerful tools for those who work in the terminal, being a perfect ally for developers and system administrators. Its main function is to allow you to manage multiple terminal sessions, windows, and panes from a single window, in addition to keeping your processes running even if your connection drops. 

Here are all the key features and concepts that tmux offers, organized by categories:

### **1. Session Persistence (The Core of tmux)** 

The most famous feature of tmux is decoupling the execution of programs from the lifecycle of your terminal emulator window.
    
- **Detachment**: You can "disconnect" (detach) from a tmux session. The terminal closes, but all your processes (servers, compilations, scripts) continue running in the background.
    
- **Attachment**: You can reconnect (attach) to that same session from anywhere (including via SSH from another computer) and find the terminal exactly as you left it.
    
- **Connection Drop Protection**: If your internet drops in the middle of a server update via SSH, the tmux session remains alive on the remote server.
    
### **2. Space Management (Sessions, Windows, and Panes)** 

tmux divides your workflow into a three-level hierarchy:
    
```text
[Session: Development]
 ├── [Window 1: Editor]
 │    ├── [Left Pane: Neovim]
 │    └── [Right Pane: Logs]
 └── [Window 2: Server]
      └── [Single Pane: Docker]
```

#### **Panes** 

They allow you to split your current screen (vertically or horizontally) into multiple smaller terminals.

- **Dynamic Splitting:** Split the screen in half as many times as you want.

- **Resizing:** Adjust the size of the panes using the keyboard.

- **Zoom Mode:** Temporarily maximize a pane to occupy the entire screen, and then minimize it back to its original position.

- **Layout Swapping:** Instantly alternate between predefined layouts (e.g., equal columns, equal rows, one main pane and other secondary ones).

#### **Windows** 

They function like the "tabs" of a web browser, occupying the entire screen.

- Each window can have its own set of panes.

- You can move panes between different windows or break a pane out into a new isolated window.

#### **Sessions** 

The highest level of organization. It allows you to separate completely different work contexts.

- You can have a session called "Web-Dev" (with windows for frontend and backend) and another called "Sysadmin" (with SSH access to servers), switching between them instantly.


### **3. Copy Mode and History (Copy Mode)** 

tmux has its own scrollback buffer, which solves the problem of terminal emulators that freeze or limit screen scrolling.

- **Keyboard Navigation**: Enter copy mode and use the arrow keys (or Vim-style shortcuts) to scroll up the screen and view the command output history.

- **Text Search**: Search for strings or regular expressions directly within the terminal history.

- **Multiple Copy Buffers**: Copy text from one pane and paste it into another. tmux keeps a history of the most recently copied texts.


### **4. Customization, Scripting, and Automation** 

tmux is highly programmable and integrates seamlessly with other terminal utilities.

- **Configuration File (`.tmux.conf`)**: Allows you to remap all shortcuts (such as changing the default prefix from `Ctrl+b` to `Ctrl+a`), change the colors of the status bar, and define default behaviors.

- **Mouse Integration**: You can enable mouse support to resize panes, switch between tabs, and scroll through history by clicking and dragging.

- **Scriptable via CLI**: Any tmux command can be executed directly from the terminal (e.g., `tmux new-window -n 'logs' 'tail -f error.log'`). This allows you to create Bash scripts that open your entire development environment with a single command.


### **5. Advanced Features**

- **Session Sharing (Pair Programming)**: Two users logged into the same server can connect to the same tmux session simultaneously. What one types, the other sees in real time.

- **Synchronize Panes**: Allows you to mirror what you type into multiple panes at the same time. Useful for running the same command on 4 different servers simultaneously.

- **Customizable Status Bar**: Shows real-time information in the footer, such as the names of active windows, CPU/Memory usage, date, time, and network connections.

- **Enter the tmux command prompt:** `Ctrl+b` then `:` (Allows you to type advanced configuration commands directly).

- **Reload configuration file** (from the tmux command prompt `:`): `source-file ~/.tmux.conf`

- **Synchronize Panes** (type the same command in all active panes simultaneously): From the command prompt `:`, type `setw synchronize-panes`

- **List all shortcut keybindings:** `Ctrl+b` then `?` 

> NOTE:
> If you are using tmux alongside `Neovim` and terminal tools, a common community recommendation is to map pane navigation so that `Ctrl+arrows` (or `hjkl`) works seamlessly to navigate both between Neovim splits and between the panes of tmux itself!


## ⚙️ Setup a Nice `.tmux.conf` Configuration

To have a nice **Tmux** like the picture below,  I create three files.
* .tmux.conf
* .tmux-os-icon.sh
* .tmux-window-icon.sh


![](_attachments/Pasted%20image%2020260617002143.png)

The `~/.tmux.conf` file is the central control script for Tmux. It executes every time you start a new Tmux server. 

```tmux
# ============================================
# Tmux Custom Configuration (~/.tmux.conf)
# ============================================

# Enables the status bar and sets the general background color (Dark Charcoal)
set -g status on
set -g status-bg "#1e1e2e"
set -g status-fg "#cdd6f4"

# Sets the bar update interval (in seconds)
set -g status-interval 5

# Window list alignment (can be left, center, or right)
set -g status-justify left

# ---------------------------------------------------------------------
# LEFT SIDE (status-left)
# Shows the current session name with a highlighted green/blue background
# ---------------------------------------------------------------------
set -g status-left-length 30
set -g status-left "#[bg=#89b4fa,fg=#11111b,bold] #(~/.tmux-os-icon.sh) #[bg=default,fg=#89b4fa] "

# ---------------------------------------------------------------------
# WINDOWS/TABS DESIGN (window-status)
# ---------------------------------------------------------------------
# How windows appearing in the background look
setw -g window-status-format "#[fg=#6c7086] #I:#W "

# How the currently ACTIVE window looks
##setw -g window-status-current-format "#[bg=#313244,fg=#f5c2e7,bold]  #I:#W* #[bg=default,fg=default]"
setw -g window-status-current-format "#[bg=#313244,fg=#f5c2e7,bold] #(~/.tmux-window-icon.sh '#W')#I:#W* #[bg=default,fg=defaul]"

# ---------------------------------------------------------------------
# RIGHT SIDE (status-right)
# Shows the date, time, and a visual indicator
# ---------------------------------------------------------------------
set -g status-right-length 100
set -g status-right "#[fg=#45475a]#[bg=#45475a,fg=#a6e3a1]  %d/%m/%Y #[fg=#f38ba8]  %H:%M "

# =====================================================================
# EXTRA: Usability bonus to include in the file
# =====================================================================

# Enable mouse support (clicking, resizing, scrolling)
set -g mouse on

# Create a quick shortcut to reload the configuration (Ctrl+b then r)
bind r source-file ~/.tmux.conf \; display-message "Configuration reloaded!"
```

The `~/.tmux-os-icon.sh` file is responsible to replace the icons of Linux distribution.

```
#!/bin/bash

# Check Distro ID from  os-release
ID=$(awk -F= '/^ID=/ {print $2}' /etc/os-release | tr -d '"')

# Choose the icon based on OS Distro
case "$ID" in
    slackware) echo " " ;;
    redhat)    echo "󱄛 " ;;
    debian)    echo " " ;;
    arch)      echo " " ;;
    ubuntu)    echo " " ;;
    fedora)    echo " " ;;
    alpine)    echo " " ;;
    *)         echo "Linux " ;;
esac

```

The `~/.tmux-window-icon.sh` file is responsible to replace the icons on the Active Windows

```
#!/bin/bash

# Accepts the current process name (#W) as an argument
PROCESS_NAME=$1

# Chooses the icon based on the active program running in the window
case "$PROCESS_NAME" in
    bash|zsh|fish|sh) echo "  " ;; # Terminal shells
    vim|nvim|nano)    echo "󟤵 " ;; # Text editors
    ssh)              echo "󰖟 " ;; # Network / SSH connections
    git)              echo " " ;; # Version control
    python|node)      echo " " ;; # Programming environments
    *)                echo " " ;; # Default fallback icon
esac
```
## ⌨️ Tmux Command Reference

A complete list of shortcut - including session management, window switching, pane splitting, and navigating history via `Copy Mode`, are below. That complete list was created based on command `Ctrl +b` then `?`

### 🌐 Session & Client Management

- **Rename current session:** `Ctrl+b` then `$`

- **Detach the current client (leave session running in background):** `Ctrl+b` then `d`

- **Choose a session from an interactive list:** `Ctrl+b` then `s`

- **Choose and detach a client from a list:** `Ctrl+b` then `D`

- **Switch to previous client:** `Ctrl+b` then `(`

- **Switch to next client:** `Ctrl+b` then `)`

- **Switch to the last client:** `Ctrl+b` then `L`

- **Suspend the current client:** `Ctrl+b` then `Ctrl+z`

### 🪟 Window Management

- **Create a new window:** `Ctrl+b` then `c`

- **Kill current window:** `Ctrl+b` then `&`

- **Rename current window:** `Ctrl+b` then `,`

- **Move the current window:** `Ctrl+b` then `.`

- **Choose a window from an interactive list:** `Ctrl+b` then `w`

- **Select window 0 to 9:** `Ctrl+b` then `0` to `9`

- **Prompt for window index to select:** `Ctrl+b` then `'`

- **Select the next window:** `Ctrl+b` then `n`

- **Select the previous window:** `Ctrl+b` then `p`

- **Select the previously current window:** `Ctrl+b` then `l`

- **Select the next window with an alert:** `Ctrl+b` then `Alt+n`

- **Select the previous window with an alert:** `Ctrl+b` then `Alt+p`

### 🗂️ Pane Management (Splits & Navigation)

- **Split window vertically (side-by-side):** `Ctrl+b` then `"`

- **Split window horizontally (top and bottom):** `Ctrl+b` then `%`

- **Kill the active pane:** `Ctrl+b` then `x`

- **Zoom/Unzoom the active pane (maximize):** `Ctrl+b` then `z`

- **Break pane out into a brand new window:** `Ctrl+b` then `!`

- **Display pane numbers:** `Ctrl+b` then `q`

- **Search for a pane:** `Ctrl+b` then `f`

- **Select the pane above:** `Ctrl+b` then `Up Arrow`

- **Select the pane below:** `Ctrl+b` then `Down Arrow`

- **Select the pane to the left:** `Ctrl+b` then `Left Arrow`

- **Select the pane to the right:** `Ctrl+b` then `Right Arrow`

- **Select the next pane:** `Ctrl+b` then `o`

- **Move to the previously active pane:** `Ctrl+b` then `;`

- **Rotate through the panes forward:** `Ctrl+b` then `Ctrl+o`

- **Rotate through the panes in reverse:** `Ctrl+b` then `Alt+o`

- **Swap the active pane with the pane above:** `Ctrl+b` then `{`

- **Swap the active pane with the pane below:** `Ctrl+b` then `}`

- **Toggle the marked pane:** `Ctrl+b` then `m`

- **Clear the marked pane:** `Ctrl+b` then `M`

### 📐 Pane Resizing

- **Resize the pane up by 1 cell:** `Ctrl+b` then `Ctrl+Up Arrow`

- **Resize the pane down by 1 cell:** `Ctrl+b` then `Ctrl+Down Arrow`

- **Resize the pane left by 1 cell:** `Ctrl+b` then `Ctrl+Left Arrow`

- **Resize the pane right by 1 cell:** `Ctrl+b` then `Ctrl+Right Arrow`

- **Resize the pane up by 5 cells:** `Ctrl+b` then `Alt+Up Arrow`

- **Resize the pane down by 5 cells:** `Ctrl+b` then `Alt+Down Arrow`

- **Resize the pane left by 5 cells:** `Ctrl+b` then `Alt+Left Arrow`

- **Resize the pane right by 5 cells:** `Ctrl+b` then `Alt+Right Arrow`

- **Spread panes out evenly:** `Ctrl+b` then `E`

### 🎨 Layout Presets

- **Select next layout:** `Ctrl+b` then `Spacebar`

- **Set the even-horizontal layout:** `Ctrl+b` then `Alt+1`

- **Set the even-vertical layout:** `Ctrl+b` then `Alt+2`

- **Set the main-horizontal layout:** `Ctrl+b` then `Alt+3`

- **Set the main-vertical layout:** `Ctrl+b` then `Alt+4`

- **Select the tiled layout:** `Ctrl+b` then `Alt+5`

- **Set the main-horizontal-mirrored layout:** `Ctrl+b` then `Alt+6`

- **Set the main-vertical-mirrored layout:** `Ctrl+b` then `Alt+7`

### 📋 Copy Mode & Paste Buffers

- **Enter copy mode:** `Ctrl+b` then `[`

- **Enter copy mode and scroll up 1 page:** `Ctrl+b` then `PageUp`

- **Paste the most recent paste buffer:** `Ctrl+b` then `]`

- **List all paste buffers:** `Ctrl+b` then `#`

- **Choose a paste buffer from a list to paste:** `Ctrl+b` then `=`

- **Delete the most recent paste buffer:** `Ctrl+b` then `-`

### 🛠️ Utilities & Advanced

- **List all active key bindings (Help menu):** `Ctrl+b` then `?`

- **Prompt for a tmux command:** `Ctrl+b` then `:`

- **Describe a specific key binding:** `Ctrl+b` then `/`

- **Customize options:** `Ctrl+b` then `C`

- **Show a digital clock:** `Ctrl+b` then `t`

- **Show tmux log/system messages:** `Ctrl+b` then `~`

- **Send the prefix key (Ctrl+b) to an application inside tmux:** `Ctrl+b` then `Ctrl+b`

- **Reset so the visible part of the window follows the cursor:** `Ctrl+b` then `DC` _(Delete key)_

- **Move the visible window area up:** `Ctrl+b` then `Shift+Up Arrow`

- **Move the visible window area down:** `Ctrl+b` then `Shift+Down Arrow`

- **Move the visible window area left:** `Ctrl+b` then `Shift+Left Arrow`

- **Move the visible window area right:** `Ctrl+b` then `Shift+Right Arrow`


## 📚 References

The following external resources are excellent companions for expanding configuration capabilities and looking up advanced CLI commands:

- [[1] Tmuxai.dev - New Window Command Guide](https://tmuxai.dev/tmux-new-window/)
   
- [[2] Techguides.dev - CLI Tmux Guide](https://techguides.dev/knowledge-base/cli-tmux-guide)
   
- [[3] Devtooleasy.com - Tmux Cheat Sheet](https://devtooleasy.com/cheat-sheet/tmux)

- [[4] Tmux.info - Official Command Documentation](https://tmux.info/docs/commands)
   
- [[5] Vinayakg.dev - Tmux Master Guide](https://blog.vinayakg.dev/tools/tmux-master-guide.html)

- [[6] Tmux Cheat Sheet - Quick Reference Guide for All Commands | tmux Tutorial & Complete Guide](https://tmux.info/docs/cheatsheet)

- [[7] NerdFonts](https://www.nerdfonts.com/cheat-sheet)

- [[8] Tmux nerd font window name plugin](https://github.com/joshmedeski/tmux-nerd-font-window-name)

- [[9] awesome-tmux](https://github.com/rothgar/awesome-tmux)

- [[10] .tmux/README.md at master · gpakosz/.tmux · GitHub](https://github.com/gpakosz/.tmux)

- [[11] Google Gemini](https://github.com/gpakosz/.tmux)




