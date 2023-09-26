<div align="center">

# `core.esupports.hop`

### Follow Various Link Locations

`esupport.hop` handles the process of dealing with links so you don't have to



</div>

# Overview

The hop module serves to provide an easy way to follow and fix broken links with a single keypress.

By default, pressing `<CR>` in normal mode under a link will attempt to follow said link.
If the link location is found, you will be taken to the destination - if it is not, you will be
prompted with a set of actions that you can perform on the broken link.

# Configuration

* <details open>
  
  <summary><h3><code>external_filetypes</h3></code> (empty list)</summary>
  
  <div>
  
  List of strings specifying which filetypes to open in an external application,
  should the user want to open a link to such a file.
  
  </div>
  
  
  
  
  </details>

* <details open>
  
  <summary><h3><code>fuzzing_threshold</h3></code> (number)</summary>
  
  <div>
  
  This value determines the strictness of fuzzy matching when trying to fix a link.
  Zero means only exact matches will be found, and higher values mean more lenience.
  
  `0.5` is the optimal default value, and it is recommended to keep this option as-is.
  
  </div>
  
  ```lua
  0.5
  ```
  
  </details>

* <details open>
  
  <summary><h3><code>lookahead</h3></code> (boolean)</summary>
  
  <div>
  
  If true, will attempt to find a link further than your cursor on the current line,
  even if your cursor is not over the link itself.
  
  </div>
  
  ```lua
  true
  ```
  
  </details>


# Required Modules

- [`core.dirman.utils`](https://github.com/nvim-neorg/neorg/wiki/Dirman-Utils) - A set of utilities for the `core.dirman` module.
- [`core.integrations.treesitter`](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration) - A module designed to integrate Treesitter into Neorg.
- [`core.ui`](https://github.com/nvim-neorg/neorg/wiki/Core-UI) - A set of public functions to help developers create and manage UI (selection popups, prompts...) in their modules.

