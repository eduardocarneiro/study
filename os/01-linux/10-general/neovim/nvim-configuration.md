
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

1. Create `~/.config/nvim/lua/plugins/treesitter.lua`
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



## Stage 8: Context Pinning (`lua/plugins/harpoon.lua`)

* Allows instant file hopping without needing file trees or buffer hunting

1. Create `~/.config/nvim/lua/plugins/harpoon.lua`
```lua
return {
  "ThePrimeagen/harpoon",
  branch = "harpoon2",
  dependencies = { "nvim-lua/plenary.nvim" },
  config = function()
    local harpoon = require("harpoon")
    
    -- Required setup initialization
    harpoon:setup()

    -- ── KEYMAPS ──────────────────────────────────────────────────
    
    -- Mark/Append current file to the list
    vim.keymap.set("n", "<leader>a", function()
      harpoon:list():add()
    end, { desc = "Harpoon: Mark/Add File" })

    -- Toggle the floating interactive menu list
    vim.keymap.set("n", "<C-e>", function()
      harpoon.ui:toggle_quick_menu(harpoon:list())
    end, { desc = "Harpoon: Toggle Menu" })

    -- Instant switching to slots 1 through 4 via Alt + Number
    vim.keymap.set("n", "<M-1>", function() harpoon:list():select(1) end, { desc = "Harpoon: File 1" })
    vim.keymap.set("n", "<M-2>", function() harpoon:list():select(2) end, { desc = "Harpoon: File 2" })
    vim.keymap.set("n", "<M-3>", function() harpoon:list():select(3) end, { desc = "Harpoon: File 3" })
    vim.keymap.set("n", "<M-4>", function() harpoon:list():select(4) end, { desc = "Harpoon: File 4" })
  end,
}
```

**🧪 How to Test:**

* Open a file and press `<Space>a` to mark it
* Press `Ctrl + e` to open the Harpoon marked file list menu
* Repeat both steps in another file



## Stage 9: LSP & Autocompletion Engine (`lua/plugins/lsp.lua`)

* Integrates Mason, Mason-LSPConfig, nvim-lspconfig, and nvim-cmp

1. Create `~/.config/nvim/lua/plugins/lsp.lua`
```lua
return {
  -- 1. External Tools Manager (Mason)
  {
    "williamboman/mason.nvim",
    cmd = "Mason",
    build = ":MasonUpdate",
    opts = {
      ui = {
        border = "rounded",
        icons = {
          package_installed = "✓",
          package_pending = "➜",
          package_uninstalled = "✗"
        }
      }
    }
  },

  -- 2. Autocomplete Engine Ecosystem
  {
    "hrsh7th/nvim-cmp",
    event = "InsertEnter",
    dependencies = {
      "hrsh7th/cmp-nvim-lsp", -- Engine bridge for language clients
      "hrsh7th/cmp-buffer",   -- Suggestions from active buffer texts
      "hrsh7th/cmp-path",     -- Auto-completes OS directory paths
    },
    config = function()
      local cmp = require("cmp")
      cmp.setup({
        mapping = cmp.mapping.preset.insert({
          ["<C-b>"] = cmp.mapping.scroll_docs(-4),
          ["<C-f>"] = cmp.mapping.scroll_docs(4),
          ["<C-Space>"] = cmp.mapping.complete(),
          ["<CR>"] = cmp.mapping.confirm({ select = true }),
          ["<Tab>"] = cmp.mapping(function(fallback)
            if cmp.visible() then cmp.select_next_item() else fallback() end
          end, { "i", "s" }),
        }),
        sources = cmp.config.sources({
          { name = "nvim_lsp" },
          { name = "buffer" },
          { name = "path" },
        }),
        window = {
          completion = cmp.config.window.bordered(),
          documentation = cmp.config.window.bordered(),
        },
      })
    end
  },

  -- 3. The LSP Core Configurator (Connects Mason and nvim-lspconfig)
  {
    "neovim/nvim-lspconfig",
    event = { "BufReadPre", "BufNewFile" },
    dependencies = {
      "williamboman/mason-lspconfig.nvim",
      "ray-x/lsp_signature.nvim", -- Inline parameter helpers
    },
    config = function()
      -- Automatically hook engine auto-completions into every language server
      local capabilities = vim.lsp.protocol.make_client_capabilities()
      local status_cmp, cmp_nvim_lsp = pcall(require, "cmp_nvim_lsp")
      if status_cmp then
        capabilities = cmp_nvim_lsp.default_capabilities(capabilities)
      end

      -- Interactive Global Keymaps inside connected code buffers
      vim.api.nvim_create_autocmd("LspAttach", {
        group = vim.api.nvim_create_augroup("UserLspConfig", {}),
        callback = function(ev)
          local opts = { buffer = ev.buf }
          
          -- Keybindings definitions
          vim.keymap.set("n", "gd", vim.lsp.buf.definition, opts)       -- Go to Definition
          vim.keymap.set("n", "K", vim.lsp.buf.hover, opts)             -- Documentation Dock
          vim.keymap.set("n", "gr", vim.lsp.buf.references, opts)        -- Code Usage references
          vim.keymap.set("n", "<leader>rn", vim.lsp.buf.rename, opts)   -- Smart refactor rename
          vim.keymap.set("n", "<leader>ca", vim.lsp.buf.code_action, opts) -- Context fixes
          
          -- Enable Native Inlay Hints if supported by the server binary
          if vim.lsp.inlay_hint then
            vim.lsp.inlay_hint.enable(true, { bufnr = ev.buf })
          end

          -- Boot up floating signature parameters context helper
          require("lsp_signature").on_attach({
            bind = true,
            handler_opts = { border = "rounded" }
          }, ev.buf)
        end,
      })

      -- Define your target SRE/Dev Environment language matrix
      local servers = {
        lua_ls = {},         -- Neovim plugins & scripts
        pyright = {},        -- Python Automation & AI Libraries
        gopls = {},          -- Go microservices & custom SRE operators
        yamlls = {},         -- Kubernetes & Ansible
        bashls = {},         -- Automation scripts
        tflint = {},         -- Terraform / OpenTofu Infrastructure
        dockerls = {},       -- Container engine layers
        jsonls = {},         -- Configurations files
        rust_analyzer = {},  -- Systems programming
      }

      -- Initialize Mason Bridge targeting automatic dynamic deployments
      require("mason-lspconfig").setup({
        ensure_installed = vim.tbl_keys(servers),
        handlers = {
          function(server_name)
            require("lspconfig")[server_name].setup({
              capabilities = capabilities,
              settings = servers[server_name],
            })
          end,
        },
      })
    end
  }
}

```

**🧪 How to Test:**

* Run `:Mason` to verify background binary installation
* Open a Lua file, hover over a standard API function (e.g., `vim.keymap.set`), and hit `K` to view documentation

