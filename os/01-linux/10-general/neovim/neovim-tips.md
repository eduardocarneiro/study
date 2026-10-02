


```
mkdir ~/.config/nvim
```


esc :Ex to navigate

esc d - to create a directory

esc % to create a new file form nvim explorer

esc :e init.lua --> to open a init.lua file

esc shift v y p --> will copy the current line and paste in the line below
esc shift v y p c i "--> will copy the current line and paste in the line below and clean the content inside a double quotes and enter insert mode

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
how to copy a line and remove the content inside a double quote
![](Pasted%20image%2020260925152148.png)

esc shift v y p c i " --> It will select the current line copy and paste it in the next line and clean the content inside a double quotes
![](Pasted%20image%2020260925152434.png)


----

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


---
**Reload the current file**

esc :e

---
**How to return to netrw from a file**
esc :e.

---
**VIM's netrw commands**
https://gist.github.com/danidiaz/37a69305e2ed3319bfff9631175c5d0f

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


---


1. https://www.reddit.com/r/neovim/comments/1306vb2/which_file_explorer_do_you_use/

2.  search on google
![[Pasted image 20261002122608.png]]

```
As Opções mais populares de gerenciadores e exploradores de arquivos para o **Neovim** dividem-se entre ==soluções nativas, plugins tradicionais em formato de árvore (_sidebar_) e abordagens modernas em formato de buffer ou terminal==:

1. Opções Nativas (Sem Plugins)

- **Netrw** (Padrão): É o explorador de arquivos clássico que já vem integrado ao Neovim/Vim. Pode ser usado como lista de diretórios ou em formato de árvore, além de suportar conexões remotas via rede. É leve, mas pode ficar lento em projetos muito grandes e aninhados. [[1](https://www.youtube.com/watch?v=xy9sSVx2cfk&t=9), [2](https://pawelgrzybek.com/neovim-file-explorers/)]

- **Visualizador Nativo de Diretórios** (Novidade): Versões mais recentes do Neovim (como o suporte experimental/novo a partir da v0.13) trazem um visualizador de diretórios integrado, leve e com suporte a atalhos rápidos e decoradores de ícones. [[1](https://www.reddit.com/r/neovim/comments/1vz7x0v/neovim_013_is_getting_a_new_builtin_directory/)]

2. Plugins em Formato de Árvore (_Sidebar Tree_)

- **Nvim-Tree (`nvim-tree.lua`)**: Um dos plugins mais populares da comunidade. Ele simula uma barra lateral gráfica estilo IDE tradicional (como VS Code), com suporte a ícones do _Nerd Fonts_, atalhos customizáveis e navegação rápida por divisões de janela (`Ctrl + v`, `Ctrl + n`). [[1](https://www.reddit.com/r/neovim/comments/1306vb2/which_file_explorer_do_you_use/), [2](https://docs.rockylinux.org/10/books/nvchad/nvchad_ui/nvimtree/), [3](https://docs.bettervim.com/mappings/file-explorer)]

- **Neo-Tree (`neo-tree.nvim`)**: Outro grande favorito dos usuários de Neovim, muito rico em funcionalidades. Ele suporta não apenas a árvore de arquivos do projeto, mas também gerencia buffers abertos, git status e arquivos modificados diretamente na barra lateral. [[1](https://www.reddit.com/r/neovim/comments/1w685wc/best_file_tree_explorer_for_neovim/), [2](https://www.reddit.com/r/neovim/comments/1306vb2/which_file_explorer_do_you_use/)]

3. Abordagem Baseada em Buffer (Edição Direta)

- **Oil.nvim** (`stevearc/oil.nvim`): Permite que você **edite o sistema de arquivos como se fosse um arquivo de texto comum (buffer)**. Você abre uma pasta com `:Oil`, renomeia, apaga ou move linhas diretamente no buffer e basta dar `:w` para aplicar as mudanças reais no disco. É muito elogiado pela simplicidade e velocidade. [[1](https://github.com/stevearc/oil.nvim), [2](https://yeripratama.com/blog/better-file-explorer-workflow-in-neovim/)]

4. Gerenciadores de Arquivos Externos via Terminal

- **Yazi (`yazi`)**: Um gerenciador de arquivos de terminal ultrarrápido baseado em Rust (com pré-visualização de imagens/arquivos e integração com _Zoxide_), que muitos usuários configuram para abrir em uma aba/flutuante dentro do Neovim ou via tmux. [[1](https://www.reddit.com/r/neovim/comments/1w685wc/best_file_tree_explorer_for_neovim/), [2](https://daily.dev/posts/how-i-navigate-files-in-neovim-hkyv9o06n)]

- **Vifm**: Um gerenciador de arquivos em modo texto inspirado no _vifm/ranger_ (com navegação em dois painéis) que pode ser usado tanto de forma independente quanto integrado ao fluxo do Neovim. [[1](https://www.reddit.com/r/neovim/comments/1306vb2/which_file_explorer_do_you_use/)]
```


---
