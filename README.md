# op.nvim

1Password for Neovim! Create items using strings from the current buffer as fields,
and insert item reference URIs (e.g. `op://vault-name/item-name/field-name`)
directly from Neovim.

![op.nvim demo gif](https://user-images.githubusercontent.com/8648891/182396210-925c6938-4ec9-4c5b-b39c-9306d04bd6c7.gif)

## Usage

`packer.nvim`

```lua
use({ 'mrjones2014/op.nvim' })
```

`vim-plug`

```VimL
Plug 'mrjones2014/op.nvim'
```

No other setup is required, however there are a few settings you can change if needed.
Settings can be changed via the Lua API, default settings are shown below:

```lua
require('op').setup({
  -- you can change this to a full path if `op`
  -- is not on your $PATH
  op_cli_path = 'op',
  -- global_args accepts any arguments
  -- listed under "Global Flags" in
  -- `op --help` output
  global_args = {
    -- use the item cache
    '--cache',
    -- print output with no color, since we
    -- are just binding it to Lua functions
    '--no-color',
  }
})
```

## Commands

`op.nvim` adds the following editor commands:

- `:OpInsert` &emdash; Insert an item reference at current cursor position
- `:OpCreate` &emdash; Create a new item using strings in the current buffer as fields