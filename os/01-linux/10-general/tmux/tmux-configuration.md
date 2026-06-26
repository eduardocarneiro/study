
The `.tmux.conf` file is tmux's control center. It works like a startup script: every time you start a tmux server, it reads this file (usually located in the user's home folder: `~/.tmux.conf`) to apply your customization preferences, shortcuts, and default behaviors.

Below, I answer your questions in detail.

**1. What are the options for tmux.conf?**

The options you can define inside `.tmux.conf` are mainly divided into three categories of commands:

- **`set-option` (or `set`):** Defines global or session options. It affects the general behavior of tmux (e.g., enabling the mouse, changing the starting index number of windows).

- **`set-window-option` (or `setw`):** Defines specific options for windows and panes (e.g., enabling Vim-style shortcuts in copy mode, changing the background color of an active window).

- **`bind-key` (or `bind`):** Used to map or remap keyboard shortcuts (keybindings).


**2. What is possible to do with tmux.conf?**

The flexibility of tmux is huge. With `.tmux.conf`, you can:

- **Change the "Prefix" key:** Change the default `Ctrl+b` shortcut to something more ergonomic, like `Ctrl+a`.

- **Enable mouse support:** Allow you to click on tabs (windows), resize panes by dragging their edges, and use the mouse wheel to scroll through history.

- **Customize the Status Bar:** Change the colors, content, and format of what is displayed in the footer (such as CPU usage, date, time, session name).

- **Vim-style shortcuts:** Configure the copy/scroll mode to respond to classic Vim commands (`h`, `j`, `k`, `l` to navigate, `v` to select, `y` to copy).

- **Automate behaviors:** Change the base index of windows and panes to start at 1 instead of 0 (which feels much more anatomical on the keyboard).

- **Create new shortcuts:** Define specific keys to split the screen more intuitively (e.g., using `|` for vertical split and `-` for horizontal split).


**3. Configuration example to customize the status bar**

The tmux status bar is essentially divided into three parts: the left side (`status-left`), the window list in the middle (`window-status`), and the right side (`status-right`).
    

Requirements:

*  Font [JetBrainMono](https://github.com/ryanoasis/nerd-fonts/releases/latest/download/JetBrainsMono.zip)

Below is the Slackware way to do it.

```
eduardo@eoc:~$ mkdir JetBrainsMonoNerd

eduardo@eoc:~$ cd JetBrainsMonoNerd

eduardo@eoc:~/JetBrainsMonoNerd$ wget https://github.com/ryanoasis/nerd-fonts/releases/latest/download/JetBrainsMono.zip

eduardo@eoc:~/JetBrainsMonoNerd$ unzip JetBrainsMono.zip 

eduardo@eoc:~/JetBrainsMonoNerd$ su -c "mkdir -p /usr/share/fonts/TTF/JetBrainsMonoNerd"

eduardo@eoc:~/JetBrainsMonoNerd$ su -c "cp *.ttf /usr/share/fonts/TTF/JetBrainsMonoNerd/"

eduardo@eoc:~/JetBrainsMonoNerd$ fc-cache -fv

```


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
    vim|nvim|nano)    echo " " ;; # Text editors
    ssh)              echo "󰖟 " ;; # Network / SSH connections
    git)              echo " " ;; # Version control
    python|node)      echo " " ;; # Programming environments
    *)                echo " " ;; # Default fallback icon
esac
```


---

> NOTE: You can safety copy the content of the files above . After install NerdFont, your code will look like the picture below:

![](_attachments/Pasted%20image%2020260621175207.png)
