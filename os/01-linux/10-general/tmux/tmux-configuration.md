


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
