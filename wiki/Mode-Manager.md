<div align="center">

# `core.mode`

### Mode manager for Neorg





</div>

# Overview

This is an internal module designed to manage Neorg modes.

Neorg modes are a way to set certain keybindings based on the current mode.
For example, you may remap some native vim keys like `j` or `k` in a special
Neorg mode that makes your cursor move between the previous and next heading.
This way you don't have to think of a new mnemonic for each key.

- To add a mode to core.mode, use the public `add_mode("my-mode-name")`.
- To set the current mode, use the public `set_mode("my-mode-name")`.
- To retrieve the *current* mode name, use `get_mode()`.
- To retrieve the *previous* mode name, use `get_previous_mode()`.
- To retrieve *all* modes, use `get_modes()`.

If `core.neorgcmd` is loaded, `core.mode.public.add_mode()` also updates the autocompletion for the `:Neorg mode` command,
which can be used by the user to switch modes.

# Configuration

* <details open>
  
  <summary><code>current_mode</code> (string)</summary>
  
  <h6>
  
  <div>
  
  Stores the current mode
  
  </div>
  
  </h6>
  
  ```lua
  "norg"
  ```
  
  </details>

* <details open>
  
  <summary><code>previous_mode</code> (string)</summary>
  
  <h6>
  
  <div>
  
  Stores the previous mode
  
  </div>
  
  </h6>
  
  ```lua
  "norg"
  ```
  
  </details>



# Required By

- [`core.integrations.treesitter`](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration) - A module designed to integrate Treesitter into Neorg.
- [`core.keybinds`](https://github.com/nvim-neorg/neorg/wiki/User-Keybinds) - Module for managing keybindings with Neorg mode support.
- [`core.presenter`](https://github.com/nvim-neorg/neorg/wiki/Core-Presenter) - Neorg module to create gorgeous presentation slides.
