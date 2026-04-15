# Neovim Configuration

A modern Neovim setup using lazy.nvim for plugin management.

## Requirements

- Neovim >= 0.9.0
- Git
- A terminal with true color support

## Installation

1. **Backup existing config** (optional):
```bash
mv ~/.config/nvim ~/.config/nvim.bak
```

2. **Clone this repository**:
```bash
git clone https://github.com/yourusername/nvim.git ~/.config/nvim
```

3. **Install dependencies** (optional but recommended):
   - `npm` or `node` - for LSP servers and formatters
   - `rust` - for some plugins
   - `lazygit` - for the built-in git UI

4. **Install Neovim** (if not already installed):
```bash
# macOS
brew install neovim

# Ubuntu/Debian
sudo apt install neovim

# Arch Linux
sudo pacman -S neovim
```

## Features

- **Theme**: TokyoNight
- **File Explorer**: nvim-tree.lua
- **LSP Support**: nvim-lspconfig + mason (auto-installs LSP servers)
- **Autocomplete**: nvim-cmp with LSP, LuaSnip, and path completion
- **Fuzzy Finder**: Telescope with FZF
- **Git Integration**: gitsigns.nvim + lazygit.nvim
- **Status Line**: lualine.nvim
- **Tabs/Buffers**: bufferline.nvim
- **Syntax Highlighting**: nvim-treesitter
- **Formatting/Linting**: conform.nvim + nvim-lint
- **Search**: todo-comments.nvim, substitute.nvim, nvim-surround

## Keybindings

| Key | Action |
|-----|--------|
| `Space` | Leader key |
| `<C-n>` | Toggle nvim-tree |
| `<leader>ff` | Find files (Telescope) |
| `<leader>fg` | Live grep |
| `<leader>fb` | Buffer list |
| `<leader>fh` | Help tags |
| `<leader>lg` | Open lazygit |
| `<leader>ca` | LSP code actions |
| `<leader>gd` | LSP definitions |
| `<leader>gr` | LSP references |
| `<leader>ff` | Format document |
| `<leader>tm` | Toggle maximize window |
| `Ctrl-h/j/k/l` | Navigate split windows |
| `Alt-h/j` | Switch buffers |
| `gcc` | Comment line |
| `gc` | Comment selection |
| `ysiw` | Add surround word |
| `ds` | Delete surround |

## LSP Servers

Automatically installed via mason:
- `lua_ls` (Lua)
- `tsserver` (TypeScript/JavaScript)
- `rust_analyzer` (Rust)
- `gopls` (Go)
- `pyright` (Python)
- `html` / `cssls` / `jsonls` (Web)
- And more...

## Troubleshooting

If plugins fail to load, try:
```bash
nvim --headless "+Lazy! sync" +qa
```

To update plugins:
```bash
nvim
:Lazy
```

Then press `U` to update all plugins.

## Customization

- Main config: `init.lua`
- Core settings: `lua/utkarsh/core/`
- Plugins: `lua/utkarsh/plugins/`
- LSP config: `lua/utkarsh/plugins/lsp/`
