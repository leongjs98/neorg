<div align="center">

# `core.presenter`

### Powerpoint in Neorg

The presenter module creates slideshows out of notes or documents.



</div>

# Overview

The presenter module provides a special Neorg display that resembles an active slideshow
presentation.

To set it up, first be sure to set the `zen_mode` variable in the [configuration](#configuration).
Afterwards, run `:Neorg presenter start` on any Norg file. The presenter will split up your file
at each level 1 heading, and display each in a different slide.

NOTE: This module is due for a rewrite. All of its behaviour is not fully documented here as it will be
overwritten soon anyway.

# Configuration

* <details open>
  
  <summary><code>zen_mode</code> (string)</summary>
  
  <h6>
  
  <div>
  
  Zen mode plugin to use. Currenly suppported:
  
  - `zen-mode` - https://github.com/folke/zen-mode.nvim
  - `truezen` - https://github.com/Pocco81/TrueZen.nvim
  
  </div>
  
  </h6>
  
  ```lua
  ""
  ```
  
  </details>


# Required Modules

- [`core.integrations.treesitter`](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration) - A module designed to integrate Treesitter into Neorg.
- [`core.mode`](https://github.com/nvim-neorg/neorg/wiki/Mode-Manager) - Modes are a way of isolating different parts of Neorg based on the current mode.
- [`core.queries.native`](https://github.com/nvim-neorg/neorg/wiki/Queries-Module) - TS wrapper in order to fetch nodes using a custom table.
- [`core.ui`](https://github.com/nvim-neorg/neorg/wiki/Core-UI) - A set of public functions to help developers create and manage UI (selection popups, prompts...) in their modules.

