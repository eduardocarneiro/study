
---

## **How to create a new window in a tmux session**

To create a new window in tmux, use the default tmux prefix and key binding:

**Press:**  
Ctrl+b, then press **c**  
This creates a new window in the current session  
1 2 3 4 5

Quick note:  
• **Ctrl+b** is the default prefix in tmux  
• **c** means “create window”

If you prefer the command-line equivalent, you can also run:  
tmux new-window

reference:
[1-Tmuxai.dev](https://tmuxai.dev/tmux-new-window/) [2-Techguides.dev](https://techguides.dev/knowledge-base/cli-tmux-guide) [3-Devtooleasy.com](https://devtooleasy.com/cheat-sheet/tmux) [4-Tmux.info](https://tmux.info/docs/commands) [5-Vinayakg.dev](https://blog.vinayakg.dev/tools/tmux-master-guide.html)

---
## **How to rename a session in tmux**

To rename a tmux session, you can use the following commands:

- [**From within tmux**: Press `Ctrl+b`, then `$` to rename the current session.](https://www.bing.com/ck/a?!&&p=597c0d25750753afc48a3b4b61ee74b3862e7fce8f6880be1c2eb99430bd9896JmltdHM9MTc4MDAxMjgwMA&ptn=3&ver=2&hsh=4&fclid=3b8c98e2-90a9-64e6-0658-8f8a918e659b&u=a1aHR0cHM6Ly90bXV4LmFwcC9zZXNzaW9ucy8&ntb=1) 
- [**From a shell prompt**: Use `tmux rename-session -t oldname newname` to rename the session.](https://www.bing.com/ck/a?!&&p=6c2047ebdbce2991e5eb0260facffe9b324108b921ccb92fc5384ebc713f0498JmltdHM9MTc4MDAxMjgwMA&ptn=3&ver=2&hsh=4&fclid=3b8c98e2-90a9-64e6-0658-8f8a918e659b&u=a1aHR0cHM6Ly90bXV4LmluZm8vZG9jcy9jaGVhdHNoZWV0&ntb=1) 


---

## **How to rename a window in a tmux session**

You can rename a window in **tmux** in a couple of quick ways — here are the most common:

**1. Using the keyboard shortcut**

- Press **`Ctrl+b`**, then **`,`** (comma)
- Type the new window name
- Press **Enter**

**2. Using the command prompt inside tmux**

- Press **`Ctrl+b`**, then **`:`**
- Type:
    
    `rename-window my_new_name`
    
- Press **Enter**

**3. Automatically naming windows** _(optional)_  
If you want tmux to rename windows based on the running command, add this to your `~/.tmux.conf`:

##### Bash

`set-option -g automatic-rename on`

Then reload your config with:

`tmux source-file ~/.tmux.conf`

---

## **How to maximize Tmux pane**

To maximize a pane in `tmux` so it temporarily fills the entire window, press the `Prefix` key followed by `z`. [[1](https://tmuxai.dev/tmux-maximize-pane/), [2](https://sgeb.io/posts/tmux-zoom-panes/)]

- **Default Shortcut:** Press **`Ctrl` + `b`** then release and press **`z`**.
- **How it works:** This acts as a zoom toggle. Pressing the same shortcut again restores the pane to its original position and size. [[1](https://tmuxai.dev/tmux-maximize-pane/), [2](https://sgeb.io/posts/tmux-zoom-panes/)]

Alternative Commands

If you prefer using the command prompt (or want to create a custom keybinding), you can run the following commands:

- **Zoom (Maximize):** Press **`Ctrl` + `b`**, then type **`:resize-pane -Z`**.
- **Balance Layout (Optional):** If you want to return to a clean, even grid afterward, press **`Ctrl` + `b`** followed by **`E`**. [[1](https://tmuxai.dev/tmux-resize-pane/), [2](https://unix.stackexchange.com/questions/32986/how-do-i-equally-balance-tmux1-split-panes)]

For more ways to manage your terminal workflow, let me know if you would like to learn about:

- Creating custom keybindings in your `.tmux.conf` file
- Navigating between multiple panes using Vim-style keys
- Splitting windows horizontally or vertically [[1](https://willcodefor.beer/posts/tmuxmax), [2](https://www.youtube.com/watch?v=jaI3Hcw-ZaA&t=70), [3](https://www.youtube.com/watch?v=umUalToecsA&t=12)]


----


references:
[Tmux Cheat Sheet & Quick Reference | Session, window, pane and more](https://tmuxcheatsheet.com/)
[tmux Cheat Sheet - Quick Reference Guide for All Commands | tmux Tutorial & Complete Guide](https://tmux.info/docs/cheatsheet)


