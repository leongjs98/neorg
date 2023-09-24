<div align="center">

# `core.integrations.treesitter`

### Snazzy Treesitter Integration



![module-showcase](https://user-images.githubusercontent.com/76052559/151668244-9805afc4-8c50-4925-85ec-1098aff5ede6.gif)

</div>


# Configuration

* <details open>
  
  <summary><code>configure_parsers</code> (boolean)</summary>
  
  <h6>
  
  <div>
  
  If true will auto-configure the parsers to use the recommended setup.
  Set to false only if you know what you're doing, or if the setting messes
  with your personal configuration.
  
  </div>
  
  </h6>
  
  ```lua
  true
  ```
  
  </details>

* <details open>
  
  <summary><code>install_parsers</code> (boolean)</summary>
  
  <h6>
  
  <div>
  
  If true will automatically install Norg parsers if they are not present.
  
  </div>
  
  </h6>
  
  ```lua
  true
  ```
  
  </details>

* <details open>
  
  <summary><code>parser_configs</code> (table)</summary>
  
  <h6>
  
  <div>
  
  Configurations for each parser as required by `nvim-treesitter`.
  If you would like to tweak your parser configs you may do so here.
  
  </div>
  
  </h6>
  
  
  * <details>
    
    <summary><code>norg</code> (table)</summary>
    
    <h6>
    
    <div>
    
    Configuration for the mainline norg parser.
    
    </div>
    
    </h6>
    
    
    * <details>
      
      <summary><code>branch</code> (string)</summary>
      
      <br>
      
      ```lua
      "main"
      ```
      
      </details>
    * <details>
      
      <summary><code>files</code> (list)</summary>
      
      <br>
      
      
      * <details>
        
        <summary> (string)</summary>
        
        <br>
        
        ```lua
        "src/parser.c"
        ```
        
        </details>
      * <details>
        
        <summary> (string)</summary>
        
        <br>
        
        ```lua
        "src/scanner.cc"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>revision</code> (string)</summary>
      
      <br>
      
      ```lua
      "6348056b999f06c2c7f43bb0a5aa7cfde5302712"
      ```
      
      </details>
    * <details>
      
      <summary><code>url</code> (string)</summary>
      
      <br>
      
      ```lua
      "https://github.com/nvim-neorg/tree-sitter-norg"
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><code>norg_meta</code> (table)</summary>
    
    <h6>
    
    <div>
    
    Configuration for the metadata parser (used to parse the contents
    of `@document.meta` blocks).
    
    </div>
    
    </h6>
    
    
    * <details>
      
      <summary><code>branch</code> (string)</summary>
      
      <br>
      
      ```lua
      "main"
      ```
      
      </details>
    * <details>
      
      <summary><code>files</code> (list)</summary>
      
      <br>
      
      
      * <details>
        
        <summary> (string)</summary>
        
        <br>
        
        ```lua
        "src/parser.c"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>revision</code> (string)</summary>
      
      <br>
      
      ```lua
      "a479d1ca05848d0b51dd25bc9f71a17e0108b240"
      ```
      
      </details>
    * <details>
      
      <summary><code>url</code> (string)</summary>
      
      <br>
      
      ```lua
      "https://github.com/nvim-neorg/tree-sitter-norg-meta"
      ```
      
      </details>
    
    
    </details>
  
  
  </details>


# Required Modules

- [`core.highlights`](https://github.com/nvim-neorg/neorg/wiki/Core-Highlights) - Manages your highlight groups with this module.
- [`core.mode`](https://github.com/nvim-neorg/neorg/wiki/Mode-Manager) - Modes are a way of isolating different parts of Neorg based on the current mode.

# Required By

- [`core.clipboard`](https://github.com/nvim-neorg/neorg/wiki/Clipboard) - A module to manipulate and interact with the user's clipboard.
- [`core.completion`](https://github.com/nvim-neorg/neorg/wiki/Completion) - A wrapper to interface with several different completion engines.
- [`core.concealer`](https://github.com/nvim-neorg/neorg/wiki/Concealer) - Enhances the basic Neorg experience by using icons instead of text.
- [`core.esupports.hop`](https://github.com/nvim-neorg/neorg/wiki/Esupports-Hop) - "Hop" between Neorg links, following them with a single keypress.
- [`core.esupports.indent`](https://github.com/nvim-neorg/neorg/wiki/Indent) - A set of instructions for Neovim to indent Neorg documents.
- [`core.esupports.metagen`](https://github.com/nvim-neorg/neorg/wiki/Metagen) - A Neorg module for generating document metadata automatically.
- [`core.export`](https://github.com/nvim-neorg/neorg/wiki/Exporting-Files) - Exports Neorg documents into any other supported filetype.
- [`core.export.markdown`](https://github.com/nvim-neorg/neorg/wiki/Markdown-Export) - Interface for `core.export` to allow exporting to markdown.
- [`core.itero`](https://github.com/nvim-neorg/neorg/wiki/Itero) - Module designed to continue lists, headings and other iterables.
- [`core.journal`](https://github.com/nvim-neorg/neorg/wiki/Journal) - Easily track a journal within Neorg.
- [`core.looking-glass`](https://github.com/nvim-neorg/neorg/wiki/Looking-Glass) - Allows for editing of code blocks within a separate buffer.
- [`core.manoeuvre`](https://github.com/nvim-neorg/neorg/wiki/Norg-Manoeuvre) - A Neorg module for moving around different elements up and down.
- [`core.pivot`](https://github.com/nvim-neorg/neorg/wiki/Pivot) - Toggles the type of list currently under the cursor.
- [`core.presenter`](https://github.com/nvim-neorg/neorg/wiki/Core-Presenter) - Neorg module to create gorgeous presentation slides.
- [`core.promo`](https://github.com/nvim-neorg/neorg/wiki/Promo) - Promotes or demotes nestable items within Neorg files.
- [`core.qol.toc`](https://github.com/nvim-neorg/neorg/wiki/TOC) - Generates a table of contents for a given Norg buffer.
- [`core.qol.todo_items`](https://github.com/nvim-neorg/neorg/wiki/Todo-Items) - Module for implementing todo lists.
- [`core.queries.native`](https://github.com/nvim-neorg/neorg/wiki/Queries-Module) - TS wrapper in order to fetch nodes using a custom table.
- [`core.summary`](https://github.com/nvim-neorg/neorg/wiki/Summary) - Creates links to all files in any workspace.
- [`core.syntax`](https://github.com/nvim-neorg/neorg/wiki/Syntax) - Handles interaction for syntax files for code blocks.
- [`core.tangle`](https://github.com/nvim-neorg/neorg/wiki/Tangling) - An Advanced Code Block Exporter.
- [`core.upgrade`](https://github.com/nvim-neorg/neorg/wiki/Upgrade) - Converts old versions of the Norg syntax to newer ones.
