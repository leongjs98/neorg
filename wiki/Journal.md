<div align="center">

# `core.journal`

### Dear diary...

The journal module allows you to take personal notes with zero friction.



</div>

# Overview

The journal module exposes a total of six commands.
The first three, `:Neorg journal today|yesterday|tomorrow`, allow you to access entries
for a given time relative to today. A file will be opened with the respective date as a `.norg` file.

The fourth command, `:Neorg journal custom`, allows you to specify a custom date as an argument.
The date must be formatted according to the `YYYY-mm-dd` format, e.g. `2023-01-01`.

The `:Neorg journal template` command creates a template file which will be used as the base whenever
a new journal entry is created.

Last but not least, the `:Neorg journal toc open|update` commands open or create/update a Table of Contents
file found in the root of the journal. This file contains links to all other journal entries, alongside
their titles.

# Configuration

* <details open>
  
  <summary><code>journal_folder</code> (string)</summary>
  
  <h6>
  
  <div>
  
  The name for the folder in which the journal files are put.
  
  </div>
  
  </h6>
  
  ```lua
  "journal"
  ```
  
  </details>

* <details open>
  
  <summary><code>strategy</code> (string)</summary>
  
  <h6>
  
  <div>
  
  The strategy to use to create directories.
  May be "flat" (`2022-03-02.norg`), "nested" (`2022/03/02.norg`),
  a lua string with the format given to `os.date()` or a lua function
  that returns a lua string with the same format.
  
  </div>
  
  </h6>
  
  ```lua
  "nested"
  ```
  
  </details>

* <details open>
  
  <summary><code>template_name</code> (string)</summary>
  
  <h6>
  
  <div>
  
  The name of the template file to use when running `:Neorg journal template`.
  
  </div>
  
  </h6>
  
  ```lua
  "template.norg"
  ```
  
  </details>

* <details open>
  
  <summary><code>toc_format</code> (nil)</summary>
  
  <h6>
  
  <div>
  
  Formatter function used to generate the toc file.
  Receives a table that contains tables like { yy, mm, dd, link, title }.
  
  The function must return a table of strings.
  
  </div>
  
  </h6>
  
  ```lua
  nil
  ```
  
  </details>

* <details open>
  
  <summary><code>use_template</code> (boolean)</summary>
  
  <h6>
  
  <div>
  
  Whether to apply the template file to new journal entries.
  
  </div>
  
  </h6>
  
  ```lua
  true
  ```
  
  </details>

* <details open>
  
  <summary><code>workspace</code> (nil)</summary>
  
  <h6>
  
  <div>
  
  Which workspace to use for the journal files, the default behaviour
  is to use the current workspace.
  
  It is recommended to set this to a static workspace, but the most optimal
  behaviour may vary from workflow to workflow.
  
  </div>
  
  </h6>
  
  ```lua
  nil
  ```
  
  </details>


# Required Modules

- [`core.dirman`](https://github.com/nvim-neorg/neorg/wiki/Dirman) - This module is be responsible for managing directories full of .norg files.
- [`core.integrations.treesitter`](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration) - A module designed to integrate Treesitter into Neorg.

