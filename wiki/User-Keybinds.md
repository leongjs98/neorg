<div align="center">

# `core.keybinds`

### The Language of Neorg

`core.keybinds` manages mappings for operations on or in `.norg` files.



</div>

# Overview

The keybind module acts as both an interface to the user and as an interface to other modules.
External modules can ask `core.keybinds` to reserve a specific keybind name, after which
`core.keybinds` passes control to you (the user) to specify what key this should be bound to.

Because of this client/server model, you must define your own `hook` function, which can
set/overwrite several keybindings to your personal preference. Below is some information
on how to disable keybinds and how to set up a keybind hook.

### Disabling Default Keybinds
By default when you load the `core.keybinds` module all keybinds will be enabled.
If you would like to change this, be sure to set `default_keybinds` to `false`:
```lua
["core.keybinds"] = {
    config = {
        default_keybinds = false,
    }
}
```

### Setting Up a Keybind Hook
To change some keybinds, you must set up a keybind hook. Below is an example
on how to do so, alongside a bunch of functions exposed to you that you can invoke
to finely control what gets set and where:
```lua
["core.keybinds"] = {
    config = {
        hook = function(keybinds)
            -- Unmaps any Neorg key from the `norg` mode
            keybinds.unmap("norg", "n", "gtd")

            -- Binds the `gtd` key in `norg` mode to execute `:echo 'Hello'`
            keybinds.map("norg", "n", "gtd", "<cmd>echo 'Hello!'<CR>")

            -- Remap unbinds the current key then rebinds it to have a different action
            -- associated with it.
            -- The following is the equivalent of the `unmap` and `map` calls you saw above:
            keybinds.remap("norg", "n", "gtd", "<cmd>echo 'Hello!'<CR>")

            -- Sometimes you may simply want to rebind the Neorg action something is bound to
            -- versus remapping the entire keybind. This remap is essentially the same as if you
            -- did `keybinds.remap("norg", "n", "<C-Space>, "<cmd>Neorg keybind norg core.qol.todo_items.todo.task_done<CR>")
            keybinds.remap_event("norg", "n", "<C-Space>", "core.qol.todo_items.todo.task_done")

            -- Want to move one keybind into the other? `remap_key` moves the data of the
            -- first keybind to the second keybind, then unbinds the first keybind.
            keybinds.remap_key("norg", "n", "<C-Space>", "<Leader>t")
        end,
    }
}
```

# Configuration

* <details open>
  
  <summary><code>default_keybinds</code> (boolean)</summary>
  
  <h6>
  
  <div>
  
  Whether to use the default keybinds provided [here](https://github.com/nvim-neorg/neorg/blob/main/lua/neorg/modules/core/keybinds/keybinds.lua).
  
  </div>
  
  </h6>
  
  ```lua
  true
  ```
  
  </details>

* <details open>
  
  <summary><code>hook</code> (nil)</summary>
  
  <h6>
  
  <div>
  
  Function to be invoked that allows the user to change their keybinds.
  See the [section on setting up a keybind hook](#setting-up-a-keybind-hook) for more details.
  
  </div>
  
  </h6>
  
  ```lua
  nil
  ```
  
  </details>

* <details open>
  
  <summary><code>keybind_preset</code> (string)</summary>
  
  <h6>
  
  <div>
  
  The keybind preset to use.
  
  This is only partially supported, and will be fully applicable in a future rewrite.
  For now it is recommended not to touch this setting.
  
  </div>
  
  </h6>
  
  ```lua
  "neorg"
  ```
  
  </details>

* <details open>
  
  <summary><code>keybind_presets</code> (empty list)</summary>
  
  <h6>
  
  <div>
  
  An array of functions, each one corresponding to a separate preset.
  
  Also currently partially supported, should not be touched.
  
  </div>
  
  </h6>
  
  
  
  
  </details>

* <details open>
  
  <summary><code>neorg_leader</code> (string)</summary>
  
  <h6>
  
  <div>
  
  The prefix to use for all Neorg keybinds.
  
  By default, this is the local leader key, which you must bind manually.
  
  </div>
  
  </h6>
  
  ```lua
  "<LocalLeader>"
  ```
  
  </details>


# Required Modules

- [`core.autocommands`](https://github.com/nvim-neorg/neorg/wiki/Autocommands) - Handles the creation and management of Neovim's autocommands.
- [`core.mode`](https://github.com/nvim-neorg/neorg/wiki/Mode-Manager) - Modes are a way of isolating different parts of Neorg based on the current mode.
- [`core.neorgcmd`](https://github.com/nvim-neorg/neorg/wiki/Neorgcmd-Module) - This module deals with handling everything related to the `:Neorg` command.

# Required By

- [`core.manoeuvre`](https://github.com/nvim-neorg/neorg/wiki/Norg-Manoeuvre) - A Neorg module for moving around different elements up and down.
