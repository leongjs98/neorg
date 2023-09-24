<div align="center">

# `core.syntax`

### Where Treesitter can't Reach

When a language not supported by Treesitter is found a fallback is made to use vim regex highlighting.



</div>

# Overview

The `core.syntax` module highlights any `@code` region where there is no treesitter parser present
to highlight the region.

This module very closely resembles the [`concealer`](https://github.com/nvim-neorg/neorg/wiki/Concealer), but some parts have been
adapted to fit the correct use case.

##### Author's note:

This module will appear as spaghetti code at first glance. This is intentional.
If one needs to edit this module, it is best to talk to me at `katawful` on GitHub.
Any edit is assumed to break this module.

# Configuration

* <details open>
  
  <summary><code>performance</code> (table)</summary>
  
  <h6>
  
  <div>
  
  Performance options for highlighting.
  
  These options exhibit the same behaviour as the [`concealer`](https://github.com/nvim-neorg/neorg/wiki/Concealer)'s.
  
  </div>
  
  </h6>
  
  
  * <details>
    
    <summary><code>increment</code> (number)</summary>
    
    <h6>
    
    <div>
    
    How many lines each "chunk" of a file should take up.
    
    When the size of the buffer is greater than this value,
    the buffer is then broken up into equal chunks and operations
    are done individually on those chunks.
    
    </div>
    
    </h6>
    
    ```lua
    1250
    ```
    
    </details>
  * <details>
    
    <summary><code>interval</code> (number)</summary>
    
    <h6>
    
    <div>
    
    How long the syntax module should wait before starting to conceal
    a new chunk.
    
    </div>
    
    </h6>
    
    ```lua
    500
    ```
    
    </details>
  * <details>
    
    <summary><code>max_debounce</code> (number)</summary>
    
    <h6>
    
    <div>
    
    The maximum amount of recalculations that take place at a single time.
    More operations than this count will be dropped.
    
    Especially useful when e.g. holding down `x` in a buffer, forcing
    hundreds of recalculations at a time.
    
    </div>
    
    </h6>
    
    ```lua
    5
    ```
    
    </details>
  * <details>
    
    <summary><code>timeout</code> (number)</summary>
    
    <h6>
    
    <div>
    
    How long the syntax module should wait before starting to conceal
    the buffer.
    
    </div>
    
    </h6>
    
    ```lua
    0
    ```
    
    </details>
  
  
  </details>


# Required Modules

- [`core.autocommands`](https://github.com/nvim-neorg/neorg/wiki/Autocommands) - Handles the creation and management of Neovim's autocommands.
- [`core.integrations.treesitter`](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration) - A module designed to integrate Treesitter into Neorg.

