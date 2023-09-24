<div align="center">

# `core.export.markdown`

### Neorg's Markdown Exporter





</div>

# Overview

This module exists as an interface for `core.export` to export `.norg` files to Markdown.
As a user the only reason you would ever have to touch this module is to configure *how* you'd
like your markdown to be exported (i.e. do you want to support certain extensions during the export).
To learn more about configuration, consult the [relevant section](#configuration).

# Configuration

* <details open>
  
  <summary><code>extension</code> (string)</summary>
  
  <h6>
  
  <div>
  
  Used by the exporter to know what extension to use
  when creating markdown files.
  The default is recommended, although you can change it.
  
  </div>
  
  </h6>
  
  ```lua
  "md"
  ```
  
  </details>

* <details open>
  
  <summary><code>extensions</code> (empty list)</summary>
  
  <h6>
  
  <div>
  
  Any extensions you may want to use when exporting to markdown. By
  default no extensions are loaded (the exporter is commonmark compliant).
  You can also set this value to `"all"` to enable all extensions.
  The full extension list is: `todo-items-basic`, `todo-items-pending`, `todo-items-extended`,
  `definition-lists`, `mathematics` and 'metadata'.
  
  </div>
  
  </h6>
  
  
  
  
  </details>

* <details open>
  
  <summary><code>mathematics</code> (table)</summary>
  
  <h6>
  
  <div>
  
  Data about how to render mathematics.
  The default is recommended as it is the most common, although certain flavours
  of markdown use different syntax.
  
  </div>
  
  </h6>
  
  
  * <details>
    
    <summary><code>block</code> (table)</summary>
    
    <h6>
    
    <div>
    
    Block-level mathematics are represented as such:
    
    ```md
    $$
    \frac{3, 2}
    $$
    ```
    
    </div>
    
    </h6>
    
    
    * <details>
      
      <summary><code>end</code> (string)</summary>
      
      <br>
      
      ```lua
      "$$"
      ```
      
      </details>
    * <details>
      
      <summary><code>start</code> (string)</summary>
      
      <br>
      
      ```lua
      "$$"
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><code>inline</code> (table)</summary>
    
    <h6>
    
    <div>
    
    Inline mathematics are represented `$like this$`.
    
    </div>
    
    </h6>
    
    
    * <details>
      
      <summary><code>end</code> (string)</summary>
      
      <br>
      
      ```lua
      "$"
      ```
      
      </details>
    * <details>
      
      <summary><code>start</code> (string)</summary>
      
      <br>
      
      ```lua
      "$"
      ```
      
      </details>
    
    
    </details>
  
  
  </details>

* <details open>
  
  <summary><code>metadata</code> (table)</summary>
  
  <h6>
  
  <div>
  
  Data about how to render metadata
  There are a few ways to render metadata blocks, but this is the most
  common.
  
  </div>
  
  </h6>
  
  
  * <details>
    
    <summary><code>end</code> (string)</summary>
    
    <br>
    
    ```lua
    "---"
    ```
    
    </details>
  * <details>
    
    <summary><code>start</code> (string)</summary>
    
    <br>
    
    ```lua
    "---"
    ```
    
    </details>
  
  
  </details>


# Required Modules

- [`core.integrations.treesitter`](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration) - A module designed to integrate Treesitter into Neorg.

