
Here, It divides the `nvim` configuration into **progressive stages** , provides a test case for each new feature added.


# 🚀 Modular Neovim Configuration Guide
```
~/.config/nvim/
├── init.lua
├── lazy-lock.json
└── lua/
    ├── config/
    │   ├── keybinds.lua
    │   ├── lazy.lua
    │   └── options.lua
    └── plugins/
        ├── colors.lua
        ├── harpoon.lua
        ├── lsp.lua
        ├── oneliners.lua
        ├── telescope.lua
        └── treesitter.lua
```

## Stage 1: Basic Bootstrapping (`init.lua`)

Create `~/.config/nvim/init.lua`
```
require('config.options')
require('config.keybinds')
require('config.lazy')
```

## Stage 2: Core Options (`lua/config/options.lua`)

* Sets up line numbers, relative jumping, and tab settings

1. Create `~/.config/nvim/lua/config/options.lua`
```
vim.opt.number = true
vim.opt.cursorline = true
vim.opt.relativenumber = true
vim.opt.shiftwidth = 4
```

2. Call it in `init.lua` file  - (not required, just explanation)
```
require("config.options")
```

**🧪 How to Test:**

- Open Neovim. Verify line numbers and relative line numbers are visible on the left.
- Write `if true then` and hit `<CR>`. Verify indent is **4 spaces** instead of 8

