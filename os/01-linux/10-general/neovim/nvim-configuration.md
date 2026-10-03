
Here, It divides the `nvim` configuration into **progressive stages** , provides a test case for each new feature added.


# 🚀 Modular Neovim Configuration Guide
```txt
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
```lua
require('config.options')
require('config.keybinds')
require('config.lazy')
```


## Stage 2: Core Options (`lua/config/options.lua`)

* Sets up line numbers, relative jumping, and tab settings

1. Create `~/.config/nvim/lua/config/options.lua`
```lua
vim.opt.number = true
vim.opt.cursorline = true
vim.opt.relativenumber = true
vim.opt.shiftwidth = 4
```

2. Call it in `init.lua` file  - (not required, just explanation. It was done on Stage1)
```lua
require("config.options")
```

**🧪 How to Test:**

- Open Neovim. Verify line numbers and relative line numbers are visible on the left.
- Write `if true then` and hit `<CR>`. Verify indent is **4 spaces** instead of 8


## Stage 3: Core Mappings (`lua/config/keybinds.lua`)

* Configures the `<leader>` key (Space) and core system mappings - (`<leader>` means "space")

1. Create `~/.config/nvim/lua/config/keybinds.lua`
```lua
vim.g.mapleader = " "
vim.keymap.set("n", "<leader>cd", vim.cmd.Ex)
```

2. Call it in (`init.lua`) - (not required, just explanation. It was done on Stage1)
```lua
require("config.keybinds")
```

**🧪 How to Test:**

* In normal mode, press `<Space>cd`.
* Netrw (the native file manager) should immediately open



## Stage 4: Plugin Manager (`lua/config/lazy.lua`)

* Installs and boots `lazy.nvim`

1. Create `~/.config/nvim/lua/config/lazy.lua`
```lua
-- Bootstrap lazy.nvim
local lazypath = vim.fn.stdpath("data") .. "/lazy/lazy.nvim"
if not (vim.uv or vim.loop).fs_stat(lazypath) then
  local lazyrepo = "https://github.com/folke/lazy.nvim.git"
  local out = vim.fn.system({ "git", "clone", "--filter=blob:none", "--branch=stable", lazyrepo, lazypath })
  if vim.v.shell_error ~= 0 then
    vim.api.nvim_echo({
      { "Failed to clone lazy.nvim:\n", "ErrorMsg" },
      { out, "WarningMsg" },
      { "\nPress any key to exit..." },
    }, true, {})
    vim.fn.getchar()
    os.exit(1)
  end
end
vim.opt.rtp:prepend(lazypath)

-- Setup lazy.nvim
require("lazy").setup({
  spec = {
    -- import your plugins
    { import = "plugins" },
  },
  change_detection = { notify = false},
})
```

2. Call `require("config.lazy")` in `init.lua` - (not required, just explanation. It was done on Stage1) 
```lua
require('config.lazy')
```

🧪 How to Test:  

* Restart Neovim and run `:Lazy`
* The `lazy.nvim` UI control panel should open


## Stage 5: Aesthetics (`lua/plugins/colors.lua`)

* Configures `tokyonight` theme and `lualine` status bar

1. Create `~/.config/nvim/lua/plugins/colors.lua`
```lua
local function enable_transparency()
    vim.api.nvim_set_hl(0, "Normal", { bg = "none"})
end
return {
    {
        "folke/tokyonight.nvim",
        config = function()
            vim.cmd.colorscheme "tokyonight"
            enable_transparency()
        end
    },
    {
        "nvim-lualine/lualine.nvim",
        dependencies = {
            "nvim-tree/nvim-web-devicons",
        },
        opts = {
            theme = 'tokyonight',
        }
    },
}
```


🧪 How to Test:

* Open Neovim. The theme should automatically switch to `tokyonight` with background transparency active and `lualine` active at the bottom



## Stage 6: Fuzzy Finder (`lua/plugins/telescope.lua`)

* Installs Telescope for searching files, buffers, and text

1. Create `~/.config/nvim/lua/plugins/telescope.lua`
```lua
return {
    'nvim-telescope/telescope.nvim', version = '*',
    dependencies = {
        'nvim-lua/plenary.nvim',
        -- optional but recommended
        { 'nvim-telescope/telescope-fzf-native.nvim', build = 'make' },
    },
    config = function()
        local builtin = require('telescope.builtin')
        vim.keymap.set('n', '<leader>ff', builtin.find_files, { desc = 'Telescope find files' })
        vim.keymap.set('n', '<leader>fg', builtin.live_grep, { desc = 'Telescope live grep' })
        vim.keymap.set('n', '<leader>fb', builtin.buffers, { desc = 'Telescope buffers' })
        vim.keymap.set('n', '<leader>fh', builtin.help_tags, { desc = 'Telescope help tags' })
    end
    }
```

**🧪 How to Test:**

* Press `<Space>ff` to open file search.
* Press `<Space>fg` and type a keyword to search text across all project files



## Stage 7: AST Syntax Parsing (`lua/plugins/treesitter.lua`)

* Provides high-speed AST syntax highlighting and indent support

```lua
return {
    'nvim-treesitter/nvim-treesitter',               
    build = ':TSUpdate',
    config = function()
        local configs = require("nvim-treesitter.configs")                                                
        configs.setup({
            highlight = {
                enable = true,                       
            },
            indent = { enable = true },              
            autotage = { enable = true},             
            -- list of supported languages https://github.com/nvim-treesitter/nvim-treesitter/blob/main/SUPPORTED_LANGUAGES.md      
            ensure_installed = {                     
                "lua",
                "javascript",                        
                "yaml",
                "bash",
                "c",
                "cpp",
                "terraform",                         
                "rust",
                "python",
                "go",
                "json",
                "sql",
                "solidity",                          
                "tmux",
                "vim",
                "ruby",
                "php",
                "mermaid",                           
                "jinja",
                "java",
                "awk",
                "css",
                "dockerfile",                        
                "groovy",
                "helm",
                "html",
                "typescript",                        
            },
            auto_install = false,                    
        })
    end
}
```

**🧪 How to Test:**

* Open a Lua file and run `:InspectTree`
* An AST syntax tree split window should appear on the left side of your editor