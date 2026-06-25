


```
mkdir ~/.config/nvim
```


esc :Ex to navigate

esc d - to create a directory

esc % to create a new file form nvim explorer

esc :e init.lua --> to open a init.lua file

esc shift v G --> to select all line below from the cursor line

esc d --> to delete all

esc :so to reload the file

work with relative number
![[Pasted image 20260622190819.png]]
esc 6 k --> go to line "vim.opt.relativenumber = true"

![[Pasted image 20260622190930.png]]
esc 6 j --> go to line "-- comment"

---
create a `~/.config/nvim/lua/config/keybinds.lua` file
```
 vim.g.mapleader = " "
 vim.keymap.set("n", "<leader>cd", vim.cmd.Ex)
```

how to use that:
In any place type "space" + cd .It will open the screen below:
![[Pasted image 20260622200437.png]]

---

how to copy a line and edit from a specific place
![[Pasted image 20260622192039.png]]
esc shift v y p --> It copy and paste the line
![[Pasted image 20260622192419.png]]
esc f . w c w-->It delete the word "options"
f . --> first instnace of "."
w --> move to the next word
![[Pasted image 20260622194020.png]]
c w --> to change that word
![[Pasted image 20260622194143.png]]

----
to indent 
![[Pasted image 20260622204857.png]]

esc = a p
![[Pasted image 20260622204943.png]]

---

How to copy the line below and edit the content inside double quote

init.lua
```
print("I use neovim, eoc")
```

ESC - Shift + v y p c i "



To source the file you are editing

esc + :so

📚 References

The following external resources are excellent companions for expanding configuration capabilities and looking up advanced CLI commands:

- [[1] Neovim Manual in Video by TJ](https://www.youtube.com/watch?v=rT-fbLFOCy0)
- [[2] How to Install and Configure Neovim (2026 Edition) | Full IDE Guide](https://www.youtube.com/watch?v=46z_h4bNzjk)
   
---
Install Ripgrep

```
root@eoc:~# sbopkg -g ripgrep
Searching for ripgrep
Found the following matches for ripgrep:
NAME            VERSION
system/ripgrep  15.1.0
root@eoc:~# sbopkg -i ripgrep
```



reltio
40/h

---
harpoon.lua

![[Pasted image 20260624231422.png]] 

<leader>  ff --> find a file e.g harpoon.lua 
<leader>  a --> to add it to harpoon list
<leader>  ff --> find a file e.g telescope.lua
<leader>  a --> to add it to harpoon list
ctrl e --> to show harpoon list







