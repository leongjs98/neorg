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
  
  <summary><h6><code>delimiter</h6></code> (string)</summary>
  
  <div>
  
  Custom delimiter between tag and value
  
  </div>
  
  ```lua
  ": "
  ```
  
  </details>

* <details open>
  
  <summary><h6><code>tab</h6></code> (string)</summary>
  
  <div>
  
  How to generate a tabulation inside the `@document.meta` tag
  
  </div>
  
  ```lua
  ""
  ```
  
  </details>

* <details open>
  
  <summary><h6><code>template</h6></code> (nil)</summary>
  
  <div>
  
  Custom template to use for generating content inside `@document.meta` tag
  
  </div>
  
  ```lua
  default_template
  ```
  
  </details>

* <details open>
  
  <summary><h6><code>type</h6></code> (string)</summary>
  
  <div>
  
  One of "none", "auto" or "empty"
  - "none" generates no metadata
  - "auto" generates metadata if it is not present
  - "empty" generates metadata only for new files/buffers.
  
  </div>
  
  ```lua
  "none"
  ```
  
  </details>

* <details open>
  
  <summary><h6><code>update_date</h6></code> (boolean)</summary>
  
  <div>
  
  Whether updated date field should be automatically updated on save if required
  
  </div>
  
  ```lua
  true
  ```
  
  </details>


# Required Modules

- [`core.autocommands`](https://github.com/nvim-neorg/neorg/wiki/Autocommands) - Handles the creation and management of Neovim's autocommands.
- [`core.integrations.treesitter`](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration) - A module designed to integrate Treesitter into Neorg.

