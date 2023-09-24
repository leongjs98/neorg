<div align="center">

# `core.completion`

### Get completions in Neorg files





</div>

# Overview


This module is an intermediary between Neorg and the completion engine of your choice. After setting up this
module (this usually just involves setting the `engine` field in the [configuration](#configuration) section),
please read the corresponding wiki page for the engine you selected ([`nvim-cmp`](https://github.com/nvim-neorg/neorg/wiki/Nvim-Cmp)
or [`nvim-compe`](https://github.com/nvim-neorg/neorg/wiki/Nvim-Compe)) to complete setup.

# Configuration

* <details open>
  
  <summary><code>engine</code> (nil)</summary>
  
  <h6>
  
  <div>
  
  The engine to use for completion.
  
  Possible values:
  - [`"nvim-cmp"`](https://github.com/nvim-neorg/neorg/wiki/Nvim-Cmp)
  - [`"nvim-compe"`](https://github.com/nvim-neorg/neorg/wiki/Nvim-Compe)
  
  </div>
  
  </h6>
  
  ```lua
  nil
  ```
  
  </details>

* <details open>
  
  <summary><code>name</code> (string)</summary>
  
  <h6>
  
  <div>
  
  The identifier for the Neorg source.
  
  </div>
  
  </h6>
  
  ```lua
  "[Neorg]"
  ```
  
  </details>


# Required Modules

- [`core.integrations.treesitter`](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration) - A module designed to integrate Treesitter into Neorg.

