<div align="center">

# `core.esupports.metagen`

### Manually Writing Metadata? No Thanks

The metagen module automatically places relevant metadata at the top of your `.norg` files.



</div>

# Overview

The metagen module exposes two commands - `:Neorg inject-metadata` and `:Neorg update-metadata`.

- The `inject-metadata` command will remove any existing metadata and overwrite it with fresh information.
- The `update-metadata` preserves existing info, updating things like the `updated` fields (when the file
  was last edited) as well as a few other non-destructive fields.

# Configuration

* <details open>
  
  <summary><code>delimiter</code> (string)</summary>
  
  <h6>
  
  <div>
  
  Custom delimiter between tag and value
  
  </div>
  
  </h6>
  
  ```lua
  ": "
  ```
  
  </details>

* <details open>
  
  <summary><code>tab</code> (string)</summary>
  
  <h6>
  
  <div>
  
  How to generate a tabulation inside the `@document.meta` tag
  
  </div>
  
  </h6>
  
  ```lua
  ""
  ```
  
  </details>

* <details open>
  
  <summary><code>template</code> (nil)</summary>
  
  <h6>
  
  <div>
  
  Custom template to use for generating content inside `@document.meta` tag
  
  </div>
  
  </h6>
  
  ```lua
  default_template
  ```
  
  </details>

* <details open>
  
  <summary><code>type</code> (string)</summary>
  
  <h6>
  
  <div>
  
  One of "none", "auto" or "empty"
  - "none" generates no metadata
  - "auto" generates metadata if it is not present
  - "empty" generates metadata only for new files/buffers.
  
  </div>
  
  </h6>
  
  ```lua
  "none"
  ```
  
  </details>

* <details open>
  
  <summary><code>update_date</code> (boolean)</summary>
  
  <h6>
  
  <div>
  
  Whether updated date field should be automatically updated on save if required
  
  </div>
  
  </h6>
  
  ```lua
  true
  ```
  
  </details>


# Required Modules

- [`core.autocommands`](https://github.com/nvim-neorg/neorg/wiki/Autocommands) - Handles the creation and management of Neovim's autocommands.
- [`core.integrations.treesitter`](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration) - A module designed to integrate Treesitter into Neorg.

