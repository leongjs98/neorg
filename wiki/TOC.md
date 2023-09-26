<div align="center">

# `core.qol.toc`

### A Bird's Eye View of Norg Documents

The TOC module geneates a table of contents for a given Norg buffer.



</div>

# Overview

<!-- TODO: make nested objects also appear nested within the TOC view (i.e. headings in headings) -->

The TOC module exposes a single command - `:Neorg toc`. This command can be executed with one of three
optional arguments: `left`, `right` and `qflist`.

When `left` or `right` is supplied, the Table of Contents split is placed on that side of the screen.
When the `qflist` argument is provided, the whole table of contents is sent to the Neovim quickfix list,
should that be more convenient for you.

When in the TOC view, `<CR>` can be pressed on any of the entries to move to that location in the respective
Norg document. The TOC view updates automatically when switching buffers.

# Configuration

* <details open>
  
  <summary><h3><code>close_after_use</h3></code> (boolean)</summary>
  
  <div>
  
  If `true`, will close the Table of Contents after an entry in the table
  is picked.
  
  </div>
  
  ```lua
  false
  ```
  
  </details>


# Required Modules

- [`core.integrations.treesitter`](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration) - A module designed to integrate Treesitter into Neorg.
- [`core.ui`](https://github.com/nvim-neorg/neorg/wiki/Core-UI) - A set of public functions to help developers create and manage UI (selection popups, prompts...) in their modules.

