<div align="center">

# `core.esupports.indent`

### Formatting on the Fly





</div>

# Overview

`core.esupports.indent` uses Norg's format to unambiguously determine
the indentation level for the current line.

The indent calculation is aided by [treesitter](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration), which
means that the quality of indents is "limited" by the quality of the produced syntax tree,
which will get better and better with time.

To reindent a file, you may use the inbuilt Neovim `=` operator.
Indent levels are also calculated as you type, but may not be entirely correct
due to incomplete syntax trees (if you find any such examples, then file an issue!).

# Configuration

* <details open>
  
  <summary><h3><code>dedent_excess</h3></code> (boolean)</summary>
  
  <div>
  
  When false will not dedent nodes, only indent them. This means that if a node
  is indented too much to the right, it will not be touched. It will only be indented
  if the node is to the left of the expected indentation level.
  
  Useful when writing documentation in the style of vimdoc, where content is indented
  heavily to the right in comparison to the default Neorg style.
  
  </div>
  
  ```lua
  true
  ```
  
  </details>

* <details open>
  
  <summary><h3><code>format_on_enter</h3></code> (boolean)</summary>
  
  <div>
  
  When true, will reformat the current line every time you press `<CR>` (Enter).
  
  </div>
  
  ```lua
  true
  ```
  
  </details>

* <details open>
  
  <summary><h3><code>format_on_escape</h3></code> (boolean)</summary>
  
  <div>
  
  When true, will reformat the current line every time you press `<Esc>` (i.e. every
  time you leave insert mode).
  
  </div>
  
  ```lua
  true
  ```
  
  </details>

* <details open>
  
  <summary><h3><code>indents</h3></code> (table)</summary>
  
  <div>
  
  The table of indentations.
  
  This table describes a set of node types and how they should be indented
  when encountered in the syntax tree.
  
  It also allows for certain nodes to be given properties (modifiers), which
  can additively stack indentation given more complex circumstances.
  
  </div>
  
  
  * <details>
    
    <summary><h3><code>_</h3></code> (table)</summary>
    
    <div>
    
    Default behaviour for every other node not explicitly defined.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>indent</h3></code> (number)</summary>
      
      <br>
      
      ```lua
      0
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>modifiers</h3></code> (list)</summary>
      
      <br>
      
      
      * <details>
        
        <summary> (string)</summary>
        
        <br>
        
        ```lua
        "under-headings"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>heading1</h3></code> (table)</summary>
    
    <div>
    
    Indent behaviour for headings.
    
    In "idiomatic norg", headings should not be indented.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>indent</h3></code> (number)</summary>
      
      <br>
      
      ```lua
      0
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>heading2</h3></code> (table)</summary>
    
    <div>
    
    Indent behaviour for headings.
    
    In "idiomatic norg", headings should not be indented.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>indent</h3></code> (number)</summary>
      
      <br>
      
      ```lua
      0
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>heading3</h3></code> (table)</summary>
    
    <div>
    
    Indent behaviour for headings.
    
    In "idiomatic norg", headings should not be indented.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>indent</h3></code> (number)</summary>
      
      <br>
      
      ```lua
      0
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>heading4</h3></code> (table)</summary>
    
    <div>
    
    Indent behaviour for headings.
    
    In "idiomatic norg", headings should not be indented.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>indent</h3></code> (number)</summary>
      
      <br>
      
      ```lua
      0
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>heading5</h3></code> (table)</summary>
    
    <div>
    
    Indent behaviour for headings.
    
    In "idiomatic norg", headings should not be indented.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>indent</h3></code> (number)</summary>
      
      <br>
      
      ```lua
      0
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>heading6</h3></code> (table)</summary>
    
    <div>
    
    Indent behaviour for headings.
    
    In "idiomatic norg", headings should not be indented.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>indent</h3></code> (number)</summary>
      
      <br>
      
      ```lua
      0
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>paragraph_segment</h3></code> (table)</summary>
    
    <div>
    
    Indent behaviour for paragraph segments (lines of text).
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>indent</h3></code> (number)</summary>
      
      <br>
      
      ```lua
      0
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>modifiers</h3></code> (list)</summary>
      
      <br>
      
      
      * <details>
        
        <summary> (string)</summary>
        
        <br>
        
        ```lua
        "under-headings"
        ```
        
        </details>
      * <details>
        
        <summary> (string)</summary>
        
        <br>
        
        ```lua
        "under-nestable-detached-modifiers"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>ranged_tag</h3></code> (table)</summary>
    
    <br>
    
    
    * <details>
      
      <summary><h3><code>indent</h3></code> (number)</summary>
      
      <br>
      
      ```lua
      0
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>modifiers</h3></code> (list)</summary>
      
      <br>
      
      
      * <details>
        
        <summary> (string)</summary>
        
        <br>
        
        ```lua
        "under-headings"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>ranged_tag_content</h3></code> (table)</summary>
    
    <div>
    
    Ranged tag contents' indentation should be calculated by Neovim itself.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>indent</h3></code> (number)</summary>
      
      <br>
      
      ```lua
      -1
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>ranged_tag_end</h3></code> (table)</summary>
    
    <div>
    
    `@end` tags should always be indented as far as the beginning `@` ranged verbatim tag.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>indent</h3></code> (function)</summary>
      
      <br>
      
      ```lua
      function(_, node)
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>strong_paragraph_delimiter</h3></code> (table)</summary>
    
    <div>
    
    Indent behaviour for strong paragraph delimiters.
    
    The indentation of these should be determined based on the heading level
    that it is a part of. Since the `strong_paragraph_delimiter` node isn't actually
    a child of the previous heading in the syntax tree some extra work is required to
    make it indent as expected.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>indent</h3></code> (function)</summary>
      
      <br>
      
      ```lua
      function(buf, _, line)
      ```
      
      </details>
    
    
    </details>
  
  
  </details>

* <details open>
  
  <summary><h3><code>modifiers</h3></code> (table)</summary>
  
  <div>
  
  Apart from indents, modifiers may also be defined.
  
  These are repeatable instructions for nodes that share common traits.
  
  </div>
  
  
  * <details>
    
    <summary><h3><code>under-headings</h3></code> (function)</summary>
    
    <div>
    
    For any object that can exist under headings
    
    </div>
    
    ```lua
    function(_, node)
    ```
    
    </details>
  * <details>
    
    <summary><h3><code>under-nestable-detached-modifiers</h3></code> (function)</summary>
    
    <div>
    
    For any object that should be indented under a list
    
    </div>
    
    ```lua
    function(_, node)
    ```
    
    </details>
  
  
  </details>

* <details open>
  
  <summary><h3><code>tweaks</h3></code> (empty list)</summary>
  
  <div>
  
  Tweaks are user defined `node_name` => `indent_level` mappings,
  allowing the user to overwrite the indentation level for certain nodes.
  
  </div>
  
  
  
  
  </details>


# Required Modules

- [`core.autocommands`](https://github.com/nvim-neorg/neorg/wiki/Autocommands) - Handles the creation and management of Neovim's autocommands.
- [`core.integrations.treesitter`](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration) - A module designed to integrate Treesitter into Neorg.

