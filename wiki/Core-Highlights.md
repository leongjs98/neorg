<div align="center">

# `core.highlights`

### No Colour Means no Productivity





</div>

# Overview

`core.highlights` maps all possible highlight groups available throughout
Neorg under a single tree of highlights: `@neorg.*`.

# Configuration

* <details open>
  
  <summary><h3><code>dim</h3></code> (table)</summary>
  
  <div>
  
  Handles the dimming of certain highlight groups.
  
  It sometimes is favourable to use an existing highlight group,
  but to dim or brighten it a little bit.
  
  To do so, you may use this table, which, similarly to the `highlights` table,
  will concatenate nested trees to form a highlight group name.
  
  The difference is, however, that the leaves of the tree are a table, not a single string.
  This table has three possible fields:
  - `reference` - which highlight to use as reference for the dimming.
  - `percentage` - by how much to darken the reference highlight. This value may be between
  `-100` and `100`, where negative percentages brighten the reference highlight, whereas
  positive values dim the highlight by the given percentage.
  
  </div>
  
  
  * <details>
    
    <summary><h3><code>markup</h3></code> (table)</summary>
    
    <br>
    
    
    * <details>
      
      <summary><h3><code>inline_comment</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>percentage</h3></code> (number)</summary>
        
        <br>
        
        ```lua
        40
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>reference</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "Normal"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>verbatim</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>percentage</h3></code> (number)</summary>
        
        <br>
        
        ```lua
        20
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>reference</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "Normal"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>tags</h3></code> (table)</summary>
    
    <br>
    
    
    * <details>
      
      <summary><h3><code>ranged_verbatim</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>code_block</h3></code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><h3><code>affect</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "background"
          ```
          
          </details>
        * <details>
          
          <summary><h3><code>percentage</h3></code> (number)</summary>
          
          <br>
          
          ```lua
          15
          ```
          
          </details>
        * <details>
          
          <summary><h3><code>reference</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "Normal"
          ```
          
          </details>
        
        
        </details>
      
      
      </details>
    
    
    </details>
  
  
  </details>

* <details open>
  
  <summary><h3><code>highlights</h3></code> (table)</summary>
  
  <div>
  
  The TS highlights for each Neorg type.
  
  The `highlights` table is a large collection of nested trees. At the leaves of each of these
  trees is the final highlight to apply to that tree. For example: `"+@comment"` tells Neorg to
  link to an existing highlight group `@comment` (denoted by the `+` prefix). When no prefix is
  found, the string is treated as arguments passed to `:highlight`, for example: `gui=bold
  fg=#000000`.
  
  Nested trees concatenate, thus:
  ```lua
  tags = {
  ranged_verbatim = {
  begin = "+@comment",
  },
  }
  ```
  matches the highlight group:
  ```lua
  @neorg.tags.ranged_verbatim.begin
  ```
  and converts into the following command:
  ```vim
  highlight! link @neorg.tags.ranged_verbatim.begin @comment
  ```
  
  </div>
  
  
  * <details>
    
    <summary><h3><code>anchors</h3></code> (table)</summary>
    
    <div>
    
    Highlights for the anchor syntax: `[name]{location}`.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>declaration</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>delimiter</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>definition</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>delimiter</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>definitions</h3></code> (table)</summary>
    
    <div>
    
    Highlights for definitions (`$ Definition`).
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>content</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@text.emphasis"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>prefix</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@punctuation.delimiter"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>suffix</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@punctuation.delimiter"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>title</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@text.strong"
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>delimiters</h3></code> (table)</summary>
    
    <div>
    
    Highlights for all the delimiter types. These include:
    - `---` - the weak delimiter
    - `===` - the strong delimiter
    - `___` - the horizontal rule
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>horizontal_line</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@punctuation.delimiter"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>strong</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@punctuation.delimiter"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>weak</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@punctuation.delimiter"
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>error</h3></code> (string)</summary>
    
    <div>
    
    In case of errors in the syntax tree, use the following highlight.
    
    </div>
    
    ```lua
    "+@error"
    ```
    
    </details>
  * <details>
    
    <summary><h3><code>footnotes</h3></code> (table)</summary>
    
    <div>
    
    Highlights for footnotes (`^ My Footnote`).
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>content</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@text.emphasis"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>prefix</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@punctuation.delimiter"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>suffix</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@punctuation.delimiter"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>title</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@text.strong"
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>headings</h3></code> (table)</summary>
    
    <div>
    
    Highlights for each individual heading level.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>1</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>prefix</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@attribute"
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>title</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@attribute"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>2</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>prefix</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@label"
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>title</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@label"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>3</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>prefix</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@constant"
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>title</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@constant"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>4</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>prefix</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@string"
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>title</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@string"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>5</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>prefix</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@label"
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>title</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@label"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>6</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>prefix</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@constructor"
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>title</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@constructor"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>links</h3></code> (table)</summary>
    
    <br>
    
    
    * <details>
      
      <summary><h3><code>description</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>delimiter</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>file</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>delimiter</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>location</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>definition</h3></code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><h3><code>prefix</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@neorg.definitions.prefix"
          ```
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><h3><code>delimiter</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>external_file</h3></code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><h3><code>prefix</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@label"
          ```
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><h3><code>footnote</h3></code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><h3><code>prefix</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@neorg.footnotes.prefix"
          ```
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><h3><code>generic</h3></code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><h3><code>prefix</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@type"
          ```
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><h3><code>heading</h3></code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><h3><code>1</h3></code> (table)</summary>
          
          <br>
          
          
          * <details>
            
            <summary><h3><code>prefix</h3></code> (string)</summary>
            
            <br>
            
            ```lua
            "+@neorg.headings.1.prefix"
            ```
            
            </details>
          
          
          </details>
        * <details>
          
          <summary><h3><code>2</h3></code> (table)</summary>
          
          <br>
          
          
          * <details>
            
            <summary><h3><code>prefix</h3></code> (string)</summary>
            
            <br>
            
            ```lua
            "+@neorg.headings.2.prefix"
            ```
            
            </details>
          
          
          </details>
        * <details>
          
          <summary><h3><code>3</h3></code> (table)</summary>
          
          <br>
          
          
          * <details>
            
            <summary><h3><code>prefix</h3></code> (string)</summary>
            
            <br>
            
            ```lua
            "+@neorg.headings.3.prefix"
            ```
            
            </details>
          
          
          </details>
        * <details>
          
          <summary><h3><code>4</h3></code> (table)</summary>
          
          <br>
          
          
          * <details>
            
            <summary><h3><code>prefix</h3></code> (string)</summary>
            
            <br>
            
            ```lua
            "+@neorg.headings.4.prefix"
            ```
            
            </details>
          
          
          </details>
        * <details>
          
          <summary><h3><code>5</h3></code> (table)</summary>
          
          <br>
          
          
          * <details>
            
            <summary><h3><code>prefix</h3></code> (string)</summary>
            
            <br>
            
            ```lua
            "+@neorg.headings.5.prefix"
            ```
            
            </details>
          
          
          </details>
        * <details>
          
          <summary><h3><code>6</h3></code> (table)</summary>
          
          <br>
          
          
          * <details>
            
            <summary><h3><code>prefix</h3></code> (string)</summary>
            
            <br>
            
            ```lua
            "+@neorg.headings.6.prefix"
            ```
            
            </details>
          
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><h3><code>marker</h3></code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><h3><code>prefix</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@neorg.markers.prefix"
          ```
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><h3><code>url</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@text.uri"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>lists</h3></code> (table)</summary>
    
    <div>
    
    Highlights for all the possible levels of ordered and unordered lists.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>ordered</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>prefix</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@repeat"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>unordered</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>prefix</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@punctuation.delimiter"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>markup</h3></code> (table)</summary>
    
    <div>
    
    Highlights for inline markup.
    
    This is all the highlights like `bold`, `italic` and so on.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>bold</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>delimiter</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>free_form_delimiter</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+NonText"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>inline_comment</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>delimiter</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>inline_math</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>delimiter</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>italic</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>delimiter</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>spoiler</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>delimiter</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>strikethrough</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>delimiter</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>subscript</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>delimiter</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>superscript</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>delimiter</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>underline</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>delimiter</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>variable</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>delimiter</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>verbatim</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>delimiter</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>modifiers</h3></code> (table)</summary>
    
    <div>
    
    Inline modifiers.
    
    This includes:
    - `~` - the trailing modifier
    - All link characters (`{`, `}`, `[`, `]`, `<`, `>`)
    - The escape character (`\`)
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>escape</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@type"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>link</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+NonText"
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>quotes</h3></code> (table)</summary>
    
    <div>
    
    Highlights for all the possible levels of quotes.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>1</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>content</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@punctuation.delimiter"
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>prefix</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@punctuation.delimiter"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>2</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>content</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+Blue"
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>prefix</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+Blue"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>3</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>content</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+Yellow"
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>prefix</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+Yellow"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>4</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>content</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+Red"
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>prefix</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+Red"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>5</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>content</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+Green"
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>prefix</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+Green"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>6</h3></code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><h3><code>content</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+Brown"
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>prefix</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+Brown"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>selection_window</h3></code> (table)</summary>
    
    <div>
    
    Highlights displayed in Neorg selection window popups.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>arrow</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@none"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>heading</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@annotation"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>key</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@namespace"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>keyname</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@constant"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>nestedkeyname</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@string"
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>tags</h3></code> (table)</summary>
    
    <div>
    
    Highlights displayed in all sorts of tag types.
    
    These include: `@`, `.`, `|`, `#`, `+` and `=`.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>carryover</h3></code> (table)</summary>
      
      <div>
      
      Highlights for the carryover (`#`, `+`) tags.
      
      </div>
      
      
      * <details>
        
        <summary><h3><code>begin</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@label"
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>name</h3></code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><h3><code>delimiter</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@none"
          ```
          
          </details>
        * <details>
          
          <summary><h3><code>word</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@label"
          ```
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><h3><code>parameters</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@string"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>comment</h3></code> (table)</summary>
      
      <div>
      
      Highlights for the content of any tag named `comment`.
      
      Most prominent use case is for the `#comment` carryover tag.
      
      </div>
      
      
      * <details>
        
        <summary><h3><code>content</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@comment"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><h3><code>ranged_verbatim</h3></code> (table)</summary>
      
      <div>
      
      Highlights for the `@` verbatim tags.
      
      </div>
      
      
      * <details>
        
        <summary><h3><code>begin</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@keyword"
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>document_meta</h3></code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><h3><code>array</h3></code> (table)</summary>
          
          <br>
          
          
          * <details>
            
            <summary><h3><code>bracket</h3></code> (string)</summary>
            
            <br>
            
            ```lua
            "+@punctuation.bracket"
            ```
            
            </details>
          * <details>
            
            <summary><h3><code>value</h3></code> (string)</summary>
            
            <br>
            
            ```lua
            "+@none"
            ```
            
            </details>
          
          
          </details>
        * <details>
          
          <summary><h3><code>authors</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@annotation"
          ```
          
          </details>
        * <details>
          
          <summary><h3><code>categories</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@keyword"
          ```
          
          </details>
        * <details>
          
          <summary><h3><code>created</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@float"
          ```
          
          </details>
        * <details>
          
          <summary><h3><code>description</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@label"
          ```
          
          </details>
        * <details>
          
          <summary><h3><code>key</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@field"
          ```
          
          </details>
        * <details>
          
          <summary><h3><code>number</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@number"
          ```
          
          </details>
        * <details>
          
          <summary><h3><code>object</h3></code> (table)</summary>
          
          <br>
          
          
          * <details>
            
            <summary><h3><code>bracket</h3></code> (string)</summary>
            
            <br>
            
            ```lua
            "+@punctuation.bracket"
            ```
            
            </details>
          
          
          </details>
        * <details>
          
          <summary><h3><code>title</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@text.title"
          ```
          
          </details>
        * <details>
          
          <summary><h3><code>trailing</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@repeat"
          ```
          
          </details>
        * <details>
          
          <summary><h3><code>updated</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@float"
          ```
          
          </details>
        * <details>
          
          <summary><h3><code>value</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@string"
          ```
          
          </details>
        * <details>
          
          <summary><h3><code>version</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@float"
          ```
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><h3><code>end</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@keyword"
        ```
        
        </details>
      * <details>
        
        <summary><h3><code>name</h3></code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><h3><code>delimiter</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@none"
          ```
          
          </details>
        * <details>
          
          <summary><h3><code>word</h3></code> (string)</summary>
          
          <br>
          
          ```lua
          "+@keyword"
          ```
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><h3><code>parameters</h3></code> (string)</summary>
        
        <br>
        
        ```lua
        "+@type"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><h3><code>todo_items</h3></code> (table)</summary>
    
    <div>
    
    Highlights for TODO items.
    
    This strictly covers the `( )` component of any detached modifier. In other words, these
    highlights only bother with highlighting the brackets and the content within, but not the
    object containing the TODO item itself.
    
    </div>
    
    
    * <details>
      
      <summary><h3><code>cancelled</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+NonText"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>done</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@string"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>on_hold</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@text.note"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>pending</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@namespace"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>recurring</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@repeat"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>uncertain</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@boolean"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>undone</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@punctuation.delimiter"
      ```
      
      </details>
    * <details>
      
      <summary><h3><code>urgent</h3></code> (string)</summary>
      
      <br>
      
      ```lua
      "+@text.danger"
      ```
      
      </details>
    
    
    </details>
  
  
  </details>


# Required Modules

- [`core.autocommands`](https://github.com/nvim-neorg/neorg/wiki/Autocommands) - Handles the creation and management of Neovim's autocommands.

# Required By

- [`core.integrations.treesitter`](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration) - A module designed to integrate Treesitter into Neorg.
