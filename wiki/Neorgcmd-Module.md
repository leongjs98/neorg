<div align="center">

# `core.neorgcmd`

### Does the Heavy Lifting for the `:Neorg` Command





</div>

# Overview

This internal module handles everything there is for the `:Neorg` command to function.

Different modules can define their own commands, completions and conditions on when they'd
like these commands to be avaiable.

For a full example on how to create your own command, it is recommended to read the
`core.neorgcmd`'s `module.lua` file. At the beginning of the file is an examples table
which walks you through the necessary steps.

# Configuration

* <details open>
  
  <summary><code>default</code> (list)</summary>
  
  <h6>
  
  <div>
  
  A list of default commands to load.
  
  This feature will soon be deprecated, so it is not recommended to touch it.
  
  </div>
  
  </h6>
  
  
  * <details>
    
    <summary> (string)</summary>
    
    <br>
    
    ```lua
    "module.list"
    ```
    
    </details>
  * <details>
    
    <summary> (string)</summary>
    
    <br>
    
    ```lua
    "module.load"
    ```
    
    </details>
  * <details>
    
    <summary> (string)</summary>
    
    <br>
    
    ```lua
    "return"
    ```
    
    </details>
  
  
  </details>

* <details open>
  
  <summary><code>load</code> (list)</summary>
  
  <h6>
  
  <div>
  
  A list of neorgcmd modules to load automatically.
  This feature will soon be deprecated, so it is not recommended to touch it.
  
  </div>
  
  </h6>
  
  
  * <details>
    
    <summary> (string)</summary>
    
    <br>
    
    ```lua
    "default"
    ```
    
    </details>
  
  
  </details>



# Required By

- [`core.keybinds`](https://github.com/nvim-neorg/neorg/wiki/User-Keybinds) - Module for managing keybindings with Neorg mode support.
- [`core.neorgcmd.commands.module.list`](https://github.com/nvim-neorg/neorg/wiki/Neorgcmd-List) - List loaded modules.
- [`core.neorgcmd.commands.module.load`](https://github.com/nvim-neorg/neorg/wiki/Neorgcmd-List) - Load a new module dynamically.
- [`core.neorgcmd.commands.return`](https://github.com/nvim-neorg/neorg/wiki/Neorgcmd-return) - Return to last location before entering Neorg.
- [`core.tangle`](https://github.com/nvim-neorg/neorg/wiki/Tangling) - An Advanced Code Block Exporter.
