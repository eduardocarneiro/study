
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
        └── treesitter.lua    # AST Structural abstract syntax tree parsing
```


📚 References

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



