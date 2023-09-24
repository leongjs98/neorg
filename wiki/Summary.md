<div align="center">

# `core.summary`

### Write notes, not boilerplate.

The summary module creates links and annotations to all files in a given workspace.



</div>

# Overview

<!-- TODO: GIF -->
The `core.summary` module exposes a single command - `:Neorg generate-workspace-summary`.

When executed with the cursor hovering over a heading, `core.summary` will generate, you guessed it,
a summary of the entire workspace, with links to each respective entry in that workspace.

The way the summary is generated relies on the `strategy` configuration option,
which by default consults the document metadata (see also
[`core.esupports.metagen`](https://github.com/nvim-neorg/neorg/wiki/Metagen)) or the first heading title
as a fallback to build up a tree of categories, titles and descriptions.

# Configuration

* <details open>
  
  <summary><code>strategy</code> (string)</summary>
  
  <h6>
  
  <div>
  
  The strategy to use to generate a summary.
  
  Possible options are:
  - "default" - read the metadata to categorize and annotate files. Files
  without metadata will use the top level heading as the title. If no headings are present, the filename will be used.
  @type string|fun(files: string[], ws_root: string, heading_level: number?): string[]?
  
  </div>
  
  </h6>
  
  ```lua
  "default"
  ```
  
  </details>


# Required Modules

- [`core.integrations.treesitter`](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration) - A module designed to integrate Treesitter into Neorg.

