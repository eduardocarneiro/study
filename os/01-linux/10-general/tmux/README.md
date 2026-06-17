
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

To have something nice like the picture below,  follow this session to setup you nice `.tmux.conf`

![[Pasted image 20260617002143.png]]

The `~/.tmux.conf` file is the central control script for Tmux. It executes every time you start a new Tmux server. 

```tmux
# ==========================================
# Tmux Custom Configuration (~/.tmux.conf)
# ==========================================


```

## ⌨️ Tmux Command Reference

A complete list of shortcut - including session management, window switching, pane splitting, and navigating history via `Copy Mode`. 


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




