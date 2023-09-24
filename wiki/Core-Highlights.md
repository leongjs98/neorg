<div align="center">

# `core.highlights`

### No Colour Means no Productivity





</div>

# Overview

`core.highlights` maps all possible highlight groups available throughout
Neorg under a single tree of highlights: `@neorg.*`.

# Configuration

* <details open>
  
  <summary><code>dim</code> (table)</summary>
  
  <h6>
  
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
  
  </h6>
  
  
  * <details>
    
    <summary><code>markup</code> (table)</summary>
    
    <br>
    
    
    * <details>
      
      <summary><code>inline_comment</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>percentage</code> (number)</summary>
        
        <br>
        
        ```lua
        40
        ```
        
        </details>
      * <details>
        
        <summary><code>reference</code> (string)</summary>
        
        <br>
        
        ```lua
        "Normal"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>verbatim</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>percentage</code> (number)</summary>
        
        <br>
        
        ```lua
        20
        ```
        
        </details>
      * <details>
        
        <summary><code>reference</code> (string)</summary>
        
        <br>
        
        ```lua
        "Normal"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><code>tags</code> (table)</summary>
    
    <br>
    
    
    * <details>
      
      <summary><code>ranged_verbatim</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>code_block</code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><code>affect</code> (string)</summary>
          
          <br>
          
          ```lua
          "background"
          ```
          
          </details>
        * <details>
          
          <summary><code>percentage</code> (number)</summary>
          
          <br>
          
          ```lua
          15
          ```
          
          </details>
        * <details>
          
          <summary><code>reference</code> (string)</summary>
          
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
  
  <summary><code>highlights</code> (table)</summary>
  
  <h6>
  
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
  
  </h6>
  
  
  * <details>
    
    <summary><code>anchors</code> (table)</summary>
    
    <h6>
    
    <div>
    
    Highlights for the anchor syntax: `[name]{location}`.
    
    </div>
    
    </h6>
    
    
    * <details>
      
      <summary><code>declaration</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>delimiter</code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>definition</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>delimiter</code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><code>definitions</code> (table)</summary>
    
    <h6>
    
    <div>
    
    Highlights for definitions (`$ Definition`).
    
    </div>
    
    </h6>
    
    
    * <details>
      
      <summary><code>content</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@text.emphasis"
      ```
      
      </details>
    * <details>
      
      <summary><code>prefix</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@punctuation.delimiter"
      ```
      
      </details>
    * <details>
      
      <summary><code>suffix</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@punctuation.delimiter"
      ```
      
      </details>
    * <details>
      
      <summary><code>title</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@text.strong"
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><code>delimiters</code> (table)</summary>
    
    <h6>
    
    <div>
    
    Highlights for all the delimiter types. These include:
    - `---` - the weak delimiter
    - `===` - the strong delimiter
    - `___` - the horizontal rule
    
    </div>
    
    </h6>
    
    
    * <details>
      
      <summary><code>horizontal_line</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@punctuation.delimiter"
      ```
      
      </details>
    * <details>
      
      <summary><code>strong</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@punctuation.delimiter"
      ```
      
      </details>
    * <details>
      
      <summary><code>weak</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@punctuation.delimiter"
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><code>error</code> (string)</summary>
    
    <h6>
    
    <div>
    
    In case of errors in the syntax tree, use the following highlight.
    
    </div>
    
    </h6>
    
    ```lua
    "+@error"
    ```
    
    </details>
  * <details>
    
    <summary><code>footnotes</code> (table)</summary>
    
    <h6>
    
    <div>
    
    Highlights for footnotes (`^ My Footnote`).
    
    </div>
    
    </h6>
    
    
    * <details>
      
      <summary><code>content</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@text.emphasis"
      ```
      
      </details>
    * <details>
      
      <summary><code>prefix</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@punctuation.delimiter"
      ```
      
      </details>
    * <details>
      
      <summary><code>suffix</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@punctuation.delimiter"
      ```
      
      </details>
    * <details>
      
      <summary><code>title</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@text.strong"
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><code>headings</code> (table)</summary>
    
    <h6>
    
    <div>
    
    Highlights for each individual heading level.
    
    </div>
    
    </h6>
    
    
    * <details>
      
      <summary><code>1</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>prefix</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@attribute"
        ```
        
        </details>
      * <details>
        
        <summary><code>title</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@attribute"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>2</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>prefix</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@label"
        ```
        
        </details>
      * <details>
        
        <summary><code>title</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@label"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>3</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>prefix</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@constant"
        ```
        
        </details>
      * <details>
        
        <summary><code>title</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@constant"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>4</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>prefix</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@string"
        ```
        
        </details>
      * <details>
        
        <summary><code>title</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@string"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>5</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>prefix</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@label"
        ```
        
        </details>
      * <details>
        
        <summary><code>title</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@label"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>6</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>prefix</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@constructor"
        ```
        
        </details>
      * <details>
        
        <summary><code>title</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@constructor"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><code>links</code> (table)</summary>
    
    <br>
    
    
    * <details>
      
      <summary><code>description</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>delimiter</code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>file</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>delimiter</code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>location</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>definition</code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><code>prefix</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@neorg.definitions.prefix"
          ```
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><code>delimiter</code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      * <details>
        
        <summary><code>external_file</code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><code>prefix</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@label"
          ```
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><code>footnote</code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><code>prefix</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@neorg.footnotes.prefix"
          ```
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><code>generic</code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><code>prefix</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@type"
          ```
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><code>heading</code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><code>1</code> (table)</summary>
          
          <br>
          
          
          * <details>
            
            <summary><code>prefix</code> (string)</summary>
            
            <br>
            
            ```lua
            "+@neorg.headings.1.prefix"
            ```
            
            </details>
          
          
          </details>
        * <details>
          
          <summary><code>2</code> (table)</summary>
          
          <br>
          
          
          * <details>
            
            <summary><code>prefix</code> (string)</summary>
            
            <br>
            
            ```lua
            "+@neorg.headings.2.prefix"
            ```
            
            </details>
          
          
          </details>
        * <details>
          
          <summary><code>3</code> (table)</summary>
          
          <br>
          
          
          * <details>
            
            <summary><code>prefix</code> (string)</summary>
            
            <br>
            
            ```lua
            "+@neorg.headings.3.prefix"
            ```
            
            </details>
          
          
          </details>
        * <details>
          
          <summary><code>4</code> (table)</summary>
          
          <br>
          
          
          * <details>
            
            <summary><code>prefix</code> (string)</summary>
            
            <br>
            
            ```lua
            "+@neorg.headings.4.prefix"
            ```
            
            </details>
          
          
          </details>
        * <details>
          
          <summary><code>5</code> (table)</summary>
          
          <br>
          
          
          * <details>
            
            <summary><code>prefix</code> (string)</summary>
            
            <br>
            
            ```lua
            "+@neorg.headings.5.prefix"
            ```
            
            </details>
          
          
          </details>
        * <details>
          
          <summary><code>6</code> (table)</summary>
          
          <br>
          
          
          * <details>
            
            <summary><code>prefix</code> (string)</summary>
            
            <br>
            
            ```lua
            "+@neorg.headings.6.prefix"
            ```
            
            </details>
          
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><code>marker</code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><code>prefix</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@neorg.markers.prefix"
          ```
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><code>url</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@text.uri"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><code>lists</code> (table)</summary>
    
    <h6>
    
    <div>
    
    Highlights for all the possible levels of ordered and unordered lists.
    
    </div>
    
    </h6>
    
    
    * <details>
      
      <summary><code>ordered</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>prefix</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@repeat"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>unordered</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>prefix</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@punctuation.delimiter"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><code>markup</code> (table)</summary>
    
    <h6>
    
    <div>
    
    Highlights for inline markup.
    
    This is all the highlights like `bold`, `italic` and so on.
    
    </div>
    
    </h6>
    
    
    * <details>
      
      <summary><code>bold</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>delimiter</code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>free_form_delimiter</code> (string)</summary>
      
      <br>
      
      ```lua
      "+NonText"
      ```
      
      </details>
    * <details>
      
      <summary><code>inline_comment</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>delimiter</code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>inline_math</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>delimiter</code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>italic</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>delimiter</code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>spoiler</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>delimiter</code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>strikethrough</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>delimiter</code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>subscript</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>delimiter</code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>superscript</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>delimiter</code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>underline</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>delimiter</code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>variable</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>delimiter</code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>verbatim</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>delimiter</code> (string)</summary>
        
        <br>
        
        ```lua
        "+NonText"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><code>modifiers</code> (table)</summary>
    
    <h6>
    
    <div>
    
    Inline modifiers.
    
    This includes:
    - `~` - the trailing modifier
    - All link characters (`{`, `}`, `[`, `]`, `<`, `>`)
    - The escape character (`\`)
    
    </div>
    
    </h6>
    
    
    * <details>
      
      <summary><code>escape</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@type"
      ```
      
      </details>
    * <details>
      
      <summary><code>link</code> (string)</summary>
      
      <br>
      
      ```lua
      "+NonText"
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><code>quotes</code> (table)</summary>
    
    <h6>
    
    <div>
    
    Highlights for all the possible levels of quotes.
    
    </div>
    
    </h6>
    
    
    * <details>
      
      <summary><code>1</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>content</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@punctuation.delimiter"
        ```
        
        </details>
      * <details>
        
        <summary><code>prefix</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@punctuation.delimiter"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>2</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>content</code> (string)</summary>
        
        <br>
        
        ```lua
        "+Blue"
        ```
        
        </details>
      * <details>
        
        <summary><code>prefix</code> (string)</summary>
        
        <br>
        
        ```lua
        "+Blue"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>3</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>content</code> (string)</summary>
        
        <br>
        
        ```lua
        "+Yellow"
        ```
        
        </details>
      * <details>
        
        <summary><code>prefix</code> (string)</summary>
        
        <br>
        
        ```lua
        "+Yellow"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>4</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>content</code> (string)</summary>
        
        <br>
        
        ```lua
        "+Red"
        ```
        
        </details>
      * <details>
        
        <summary><code>prefix</code> (string)</summary>
        
        <br>
        
        ```lua
        "+Red"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>5</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>content</code> (string)</summary>
        
        <br>
        
        ```lua
        "+Green"
        ```
        
        </details>
      * <details>
        
        <summary><code>prefix</code> (string)</summary>
        
        <br>
        
        ```lua
        "+Green"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>6</code> (table)</summary>
      
      <br>
      
      
      * <details>
        
        <summary><code>content</code> (string)</summary>
        
        <br>
        
        ```lua
        "+Brown"
        ```
        
        </details>
      * <details>
        
        <summary><code>prefix</code> (string)</summary>
        
        <br>
        
        ```lua
        "+Brown"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><code>selection_window</code> (table)</summary>
    
    <h6>
    
    <div>
    
    Highlights displayed in Neorg selection window popups.
    
    </div>
    
    </h6>
    
    
    * <details>
      
      <summary><code>arrow</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@none"
      ```
      
      </details>
    * <details>
      
      <summary><code>heading</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@annotation"
      ```
      
      </details>
    * <details>
      
      <summary><code>key</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@namespace"
      ```
      
      </details>
    * <details>
      
      <summary><code>keyname</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@constant"
      ```
      
      </details>
    * <details>
      
      <summary><code>nestedkeyname</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@string"
      ```
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><code>tags</code> (table)</summary>
    
    <h6>
    
    <div>
    
    Highlights displayed in all sorts of tag types.
    
    These include: `@`, `.`, `|`, `#`, `+` and `=`.
    
    </div>
    
    </h6>
    
    
    * <details>
      
      <summary><code>carryover</code> (table)</summary>
      
      <h6>
      
      <div>
      
      Highlights for the carryover (`#`, `+`) tags.
      
      </div>
      
      </h6>
      
      
      * <details>
        
        <summary><code>begin</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@label"
        ```
        
        </details>
      * <details>
        
        <summary><code>name</code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><code>delimiter</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@none"
          ```
          
          </details>
        * <details>
          
          <summary><code>word</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@label"
          ```
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><code>parameters</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@string"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>comment</code> (table)</summary>
      
      <h6>
      
      <div>
      
      Highlights for the content of any tag named `comment`.
      
      Most prominent use case is for the `#comment` carryover tag.
      
      </div>
      
      </h6>
      
      
      * <details>
        
        <summary><code>content</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@comment"
        ```
        
        </details>
      
      
      </details>
    * <details>
      
      <summary><code>ranged_verbatim</code> (table)</summary>
      
      <h6>
      
      <div>
      
      Highlights for the `@` verbatim tags.
      
      </div>
      
      </h6>
      
      
      * <details>
        
        <summary><code>begin</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@keyword"
        ```
        
        </details>
      * <details>
        
        <summary><code>document_meta</code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><code>array</code> (table)</summary>
          
          <br>
          
          
          * <details>
            
            <summary><code>bracket</code> (string)</summary>
            
            <br>
            
            ```lua
            "+@punctuation.bracket"
            ```
            
            </details>
          * <details>
            
            <summary><code>value</code> (string)</summary>
            
            <br>
            
            ```lua
            "+@none"
            ```
            
            </details>
          
          
          </details>
        * <details>
          
          <summary><code>authors</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@annotation"
          ```
          
          </details>
        * <details>
          
          <summary><code>categories</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@keyword"
          ```
          
          </details>
        * <details>
          
          <summary><code>created</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@float"
          ```
          
          </details>
        * <details>
          
          <summary><code>description</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@label"
          ```
          
          </details>
        * <details>
          
          <summary><code>key</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@field"
          ```
          
          </details>
        * <details>
          
          <summary><code>number</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@number"
          ```
          
          </details>
        * <details>
          
          <summary><code>object</code> (table)</summary>
          
          <br>
          
          
          * <details>
            
            <summary><code>bracket</code> (string)</summary>
            
            <br>
            
            ```lua
            "+@punctuation.bracket"
            ```
            
            </details>
          
          
          </details>
        * <details>
          
          <summary><code>title</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@text.title"
          ```
          
          </details>
        * <details>
          
          <summary><code>trailing</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@repeat"
          ```
          
          </details>
        * <details>
          
          <summary><code>updated</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@float"
          ```
          
          </details>
        * <details>
          
          <summary><code>value</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@string"
          ```
          
          </details>
        * <details>
          
          <summary><code>version</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@float"
          ```
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><code>end</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@keyword"
        ```
        
        </details>
      * <details>
        
        <summary><code>name</code> (table)</summary>
        
        <br>
        
        
        * <details>
          
          <summary><code>delimiter</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@none"
          ```
          
          </details>
        * <details>
          
          <summary><code>word</code> (string)</summary>
          
          <br>
          
          ```lua
          "+@keyword"
          ```
          
          </details>
        
        
        </details>
      * <details>
        
        <summary><code>parameters</code> (string)</summary>
        
        <br>
        
        ```lua
        "+@type"
        ```
        
        </details>
      
      
      </details>
    
    
    </details>
  * <details>
    
    <summary><code>todo_items</code> (table)</summary>
    
    <h6>
    
    <div>
    
    Highlights for TODO items.
    
    This strictly covers the `( )` component of any detached modifier. In other words, these
    highlights only bother with highlighting the brackets and the content within, but not the
    object containing the TODO item itself.
    
    </div>
    
    </h6>
    
    
    * <details>
      
      <summary><code>cancelled</code> (string)</summary>
      
      <br>
      
      ```lua
      "+NonText"
      ```
      
      </details>
    * <details>
      
      <summary><code>done</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@string"
      ```
      
      </details>
    * <details>
      
      <summary><code>on_hold</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@text.note"
      ```
      
      </details>
    * <details>
      
      <summary><code>pending</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@namespace"
      ```
      
      </details>
    * <details>
      
      <summary><code>recurring</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@repeat"
      ```
      
      </details>
    * <details>
      
      <summary><code>uncertain</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@boolean"
      ```
      
      </details>
    * <details>
      
      <summary><code>undone</code> (string)</summary>
      
      <br>
      
      ```lua
      "+@punctuation.delimiter"
      ```
      
      </details>
    * <details>
      
      <summary><code>urgent</code> (string)</summary>
      
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
