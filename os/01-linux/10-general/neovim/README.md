
# 💻 Neovim (Advanced IDE for AI SRE Automation)

Welcome to the **Neovim** engineering workspace. This module forms the primary editing core and context engine for our unified **AI SRE Setup** (`Tmux + Neovim + Local LLM + MCP + Agents`). 

By leveraging a fully modular architecture powered by `lazy.nvim`, this editor delivers immediate local compilation, deep syntax tracing, and sub-millisecond latencies when communicating with context engines running on localhost.

---


## 🏗️ Architectural Topology & File Ecosystem

The configuration is completely modularized, ensuring strict separation of concerns between core editor parameters, customized keymappings, and third-party development engines.

```text
.config/nvim/
├── init.lua                  # Primary environment bootstrap entrypoint
├── lazy-lock.json            # Lockfile detailing deterministic plugin hashes
└── lua/
    ├── config/
    │   ├── keybinds.lua      # Global custom map triggers 
    │   ├── lazy.lua          # Dependency engine bootstrap & module importer
    │   └── options.lua       # Internal runtime optimizations (relative numbers, etc.)
    └── plugins/
        ├── colors.lua        # UI Aesthetics & Statuslines (TokyoNight & Lualine)
        ├── harpoon.lua       # High-speed contextual file pinning 
        ├── lsp.lua           # Language Server Protocol infrastructure core
        ├── telescope.lua     # Fuzzy matching & text string grep systems
        ├── treesitter.lua    # AST Structural abstract syntax tree parsing
        └── new-plugin.lua    # New plugin to add more features
```

### **Is the file organization a good practice?**

**Yes, it is excellent and adheres perfectly to the modern `lazy.nvim` paradigm.**

- **Decoupled Structure:** Separating user defaults (`options.lua`, `keybinds.lua`) from external engines (`plugins/`) makes your environment incredibly easy to maintain.
    
- **Autoloading Directory:** In `lazy.lua`, the configuration sets up `{ import = "plugins" }`. This allows `lazy.nvim` to scan the `lua/plugins/` directory automatically. Any file returning a Lua table will be evaluated as a plugin specification without needing manual tracking or `require` calls inside your initialization core.


## ⌨️ Critical SRE Shortcut Reference

This deployment focuses exclusively on keyboard efficiency, keeping context switching overhead to an absolute minimum.

### 🔍 System Navigation & Workspace Scanning

|**Shortcut**|**Action**|**Core Component**|
|---|---|---|
|`<Space> cd`|Instantly drop to built-in file explorer (`:Ex`)|Neovim Core|
|`<Space> ff`|Fuzzy search file paths across workspace files|Telescope|
|`<Space> fg`|Live regex grep search across all file rows|Telescope|
|`<Space> fb`|Open interactive visualization of active buffers|Telescope|

### 🎯 Context-Pinning Navigation

|**Shortcut**|**Action**|**Core Component**|
|---|---|---|
|`<Space> a`|Pin current file to the registry slot|Harpoon 2|
|`Ctrl + e`|Toggle floating file registry modification menu|Harpoon 2|
|`Alt + 1..4`|Instant hop to pinned file slot 1 through 4|Harpoon 2|

### 🛠️ Language Engineering & Refactoring (LSP Active)

|**Shortcut**|**Action**|**Core Component**|
|---|---|---|
|`g d`|Leap to codebase definition point|Neovim LSP Client|
|`K`|Call floating documentation dock and arguments specs|Neovim LSP Client|
|`g r`|Live trace all occurrences across workspace scopes|Neovim LSP Client|
|`<Space> rn`|Global variable refactoring renaming safety sweep|Neovim LSP Client|
|`<Space> ca`|Prompts contextual code quick-fixes|Neovim LSP Client|


## 🚀 How to add more plugins using lazy.nvim properly

Because the `lazy.lua` has `{ import = "plugins" }`, the proper way to expand your setup is completely modular:

### **To add an isolated tool (e.g., an LLM integration or an auto-pair plugin):** 

Create a brand-new file under `~/.config/nvim/lua/plugins/your-new-plugin.lua` and return its spec table.
    
1. **Example structure for `lua/plugins/autopairs.lua`:**

```
-- ~/.config/nvim/lua/plugins/autopairs.lua
return {
    "windwp/nvim-autopairs",
    event = "InsertEnter",
    opts = {} -- automatically runs require("nvim-autopairs").setup({})
}
```

2. **Example structure for `lua/plugins/gp.nvim`:**

To introduce additional tools (such as local AI integrations via `gp.nvim` or structural MCP bridges) into this environment without disrupting existing systems, invoke the **Modular Spec Protocol**:
```
-- ~/.config/nvim/lua/plugins/local-ai.lua
return {
  "Robitx/gp.nvim",
  config = function()
    require("gp").setup({
      -- Target configuration parameters mapping local Ollama instances
    })
  end
}
```

Upon launching your next terminal session, `lazy.nvim` will register the delta file, download system binaries asynchronously in background environments, and inject the logic seamlessly.


## 📚 References

The following external resources are excellent companions for expanding configuration capabilities and looking up advanced CLI commands:

- [[1] Neovim Manual in Video by TJ](https://www.youtube.com/watch?v=rT-fbLFOCy0)
- [[2] How to Install and Configure Neovim (2026 Edition) | Full IDE Guide](https://www.youtube.com/watch?v=46z_h4bNzjk)
- [[3] Nvim documentation](https://neovim.io/doc/user/)
- [[4] Lsp Quickstart](https://neovim.io/doc/user/lsp/)
- [[5] Lazy.nvim Structural Specifications](https://lazy.folke.io/spec)
- [[6] Neovim LSP Engine Client API Manifest](https://neovim.io/doc/user/lsp.html)
- [[7] Mason Registry Infrastructure Index](https://github.com/williamboman/mason.nvim)
- [[8] Tree-sitter Code Parser Core Language Index](https://tree-sitter.github.io/tree-sitter/)
- [[9] ThePrimeagen Harpoon 2 Architectural Design](https://github.com/ThePrimeagen/harpoon/tree/harpoon2)



