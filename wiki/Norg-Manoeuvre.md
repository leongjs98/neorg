<div align="center">

# `core.manoeuvre`

### Move around elements easily





</div>

# Overview

### WARNING: This module is deprecated!

There is no available successor to this module yet.

# Configuration

* <details open>
  
  <summary><h3><code>moveables</h3></code> (table)</summary>
  
  <br>
  
  
  * <details>
    
    <summary><h3><code>headings</h3></code> (list)</summary>
    
    <br>
    
    
    * <details>
      
      <summary> (string)</summary>
      
      <br>
      
      ```lua
      "heading%d"
      ```
      
      </details>
    * <details>
      
      <summary> (string)</summary>
      
      <br>
      
      ```lua
      "heading%d"
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>todo_items</h3></code> (list)</summary>
    
    <br>
    
    
    * <details>
      
      <summary> (string)</summary>
      
      <br>
      
      ```lua
      "todo_item%d"
      ```
      
      </details>
    * <details>
      
      <summary> (list)</summary>
      
      <br>
      
      
      * <details>
        
        <summary> (string)</summary>
        
        <br>
        
        ```lua
        "todo_item%d"
        ```
        
        </details>
      * <details>
        
        <summary> (string)</summary>
        
        <br>
        
        ```lua
        "unordered_list%d"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>unordered_list_elements</h3></code> (list)</summary>
    
    <br>
    
    
    * <details>
      
      <summary> (string)</summary>
      
      <br>
      
      ```lua
      "unordered_list%d"
      ```
      
      </details>
    * <details>
      
      <summary> (list)</summary>
      
      <br>
      
      
      * <details>
        
        <summary> (string)</summary>
        
        <br>
        
        ```lua
        "todo_item%d"
        ```
        
        </details>
      * <details>
        
        <summary> (string)</summary>
        
        <br>
        
        ```lua
        "unordered_list%d"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  
  
  </details>


# Required Modules

- [`core.integrations.treesitter`](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration) - A module designed to integrate Treesitter into Neorg.
- [`core.keybinds`](https://github.com/nvim-neorg/neorg/wiki/User-Keybinds) - Module for managing keybindings with Neorg mode support.

