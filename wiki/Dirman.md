<div align="center">

# `core.dirman`

### The Most Critical Component of any Organized Workflow

The `dirman` module handles different collections of notes in separate directories.



</div>

# Overview

`core.dirman` provides other modules the ability to see which directories the user is in, where
each note collection is stored and how to interact with it.

When writing notes, it is often crucial to have notes on a certain topic be isolated from notes on another topic.
Dirman achieves this with a concept of "workspaces", which are named directories full of `.norg` notes.

To use `core.dirman`, simply load up the module in your configuration and specify the directories you would like to be managed for you:

```lua
require('neorg').setup {
    load = {
        ["core.defaults"] = {},
        ["core.dirman"] = {
            config = {
                workspaces = {
                    my_ws = "~/neorg", -- Format: <name_of_workspace> = <path_to_workspace_root>
                    my_other_notes = "~/work/notes",
                },
                index = "index.norg", -- The name of the main (root) .norg file
            }
        }
    }
}
```

To query the current workspace, run `:Neorg workspace`. To set the workspace, run `:Neorg workspace <workspace_name>`.

### Changing the Current Working Directory
After a recent update `core.dirman` will no longer change the current working directory after switching
workspace. To get the best experience it's recommended to set the `autochdir` Neovim option.

# Configuration

* <details open>
  
  <summary><code>default_workspace</code> (nil)</summary>
  
  <h6>
  
  <div>
  
  The default workspace to set whenever Neovim starts.
  
  </div>
  
  </h6>
  
  ```lua
  nil
  ```
  
  </details>

* <details open>
  
  <summary><code>index</code> (string)</summary>
  
  <h6>
  
  <div>
  
  The name for the index file.
  
  The index file is the "entry point" for all of your notes.
  
  </div>
  
  </h6>
  
  ```lua
  "index.norg"
  ```
  
  </details>

* <details open>
  
  <summary><code>open_last_workspace</code> (boolean)</summary>
  
  <h6>
  
  <div>
  
  Whether to open the last workspace's index file when `nvim` is executed
  without arguments.
  
  May also be set to the string `"default"`, due to which Neorg will always
  open up the index file for the workspace defined in `default_workspace`.
  
  </div>
  
  </h6>
  
  ```lua
  false
  ```
  
  </details>

* <details open>
  
  <summary><code>use_popup</code> (boolean)</summary>
  
  <h6>
  
  <div>
  
  Whether to use core.ui.text_popup for `dirman.new.note` event.
  if `false`, will use vim's default `vim.ui.input` instead.
  
  </div>
  
  </h6>
  
  ```lua
  true
  ```
  
  </details>

* <details open>
  
  <summary><code>workspaces</code> (table)</summary>
  
  <h6>
  
  <div>
  
  The list of active Neorg workspaces.
  
  There is always an inbuilt workspace called `default`, whose location is
  set to the Neovim current working directory on boot.
  
  </div>
  
  </h6>
  
  
  * <details>
    
    <summary><code>default</code> (string)</summary>
    
    <br>
    
    ```lua
    vim.fn.getcwd()
    ```
    
    </details>
  
  
  </details>


# Required Modules

- [`core.autocommands`](https://github.com/nvim-neorg/neorg/wiki/Autocommands) - Handles the creation and management of Neovim's autocommands.
- [`core.storage`](https://github.com/nvim-neorg/neorg/wiki/Storage) - Deals with storing persistent data across Neorg sessions.
- [`core.ui`](https://github.com/nvim-neorg/neorg/wiki/Core-UI) - A set of public functions to help developers create and manage UI (selection popups, prompts...) in their modules.

# Required By

- [`core.journal`](https://github.com/nvim-neorg/neorg/wiki/Journal) - Easily track a journal within Neorg.
