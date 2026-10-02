

### 🔍 Neovim NetRW file explorer

|Shortcut|Action|Core Component|
|---|---|---|
|`<F1>`|Open built-in netrw help|Vim/Neovim Netrw|
|`<CR>`|Enter selected directory or open/read file|Vim/Neovim Netrw|
|`<DEL>`|Delete selected file or directory|Vim/Neovim Netrw|
|`<C-H>`|Edit the file hiding list|Vim/Neovim Netrw|
|`<C-L>`|Refresh the current directory contents|Vim/Neovim Netrw|
|`-`|Go up one directory level (parent directory)|Vim/Neovim Netrw|
|`a`|Toggle hiding/showing filtered files|Vim/Neovim Netrw|
|`c`|Set selected directory as current working directory (`:cd`)|Vim/Neovim Netrw|
|`d`|Create a new directory (make dir)|Vim/Neovim Netrw|
|`D`|Delete selected file or directory|Vim/Neovim Netrw|
|`i`|Cycle listing style (`thin`, `long`, `wide`, `tree`)|Vim/Neovim Netrw|
|`o`|Open file in a new horizontal split|Vim/Neovim Netrw|
|`v`|Open file in a new vertical split|Vim/Neovim Netrw|
|`t`|Open file in a new tab|Vim/Neovim Netrw|
|`R`|Rename selected file or directory|Vim/Neovim Netrw|
|`x`|Execute selected file with system default program|Vim/Neovim Netrw|
|`%`|Create a new file in the current directory|Vim/Neovim Netrw|
|`mf`|Mark selected file or directory|Vim/Neovim Netrw (Mark)|
|`mF`|Unmark all marked files|Vim/Neovim Netrw (Mark)|
|`mc`|Copy marked files to target directory|Vim/Neovim Netrw (Mark)|
|`mm`|Move marked files to target directory|Vim/Neovim Netrw (Mark)|
|`md`|Run diff on marked files|Vim/Neovim Netrw (Mark)|
|`mg`|Run grep (`vimgrep`) on marked files|Vim/Neovim Netrw (Mark)|
|`mz`|Compress or decompress marked files|Vim/Neovim Netrw (Mark)|

### 🔍 System Navigation & Workspace Scanning

| **Shortcut** | **Action**                                       | **Core Component** |
| ------------ | ------------------------------------------------ | ------------------ |
| `<Space> cd` | Instantly drop to built-in file explorer (`:Ex`) | Neovim Core        |
| `<Space> ff` | Fuzzy search file paths across workspace files   | Telescope          |
| `<Space> fg` | Live regex grep search across all file rows      | Telescope          |
| `<Space> fb` | Open interactive visualization of active buffers | Telescope          |

### 🎯 Context-Pinning Navigation

| **Shortcut** | **Action**                                      | **Core Component** |
| ------------ | ----------------------------------------------- | ------------------ |
| `<Space> a`  | Pin current file to the registry slot           | Harpoon 2          |
| `Ctrl + e`   | Toggle floating file registry modification menu | Harpoon 2          |
| `Alt + 1..4` | Instant hop to pinned file slot 1 through 4     | Harpoon 2          |
|              |                                                 |                    |

### 🛠️ Language Engineering & Refactoring (LSP Active)

|**Shortcut**|**Action**|**Core Component**|
|---|---|---|
|`g d`|Leap to codebase definition point|Neovim LSP Client|
|`K`|Call floating documentation dock and arguments specs|Neovim LSP Client|
|`g r`|Live trace all occurrences across workspace scopes|Neovim LSP Client|
|`<Space> rn`|Global variable refactoring renaming safety sweep|Neovim LSP Client|
|`<Space> ca`|Prompts contextual code quick-fixes|Neovim LSP Client|
