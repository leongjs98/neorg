<div align="center">

# `core.upgrade`

### Upgrade Tool for Neorg





</div>

# Overview

When dealing with changes to the Norg syntax, it is very inconvenient to have to manually
update all of your files, especially if you're not a regex wizard.

To alleviate this problem, the upgrade tool serves as a way to automate the process.

There are two main commands that are exposed for use:
- `:Neorg upgrade current-file` - takes the current file and upgrades it to the new syntax.
  Will ask for a backup.
- `:Neorg upgrade current-directory` - upgrades all files in the current directory. Asks
   for a backup and displays the current directory so no mistakes are made.

When a backup is requested, Neorg backs up the file to `<filename>.old.norg`, then upgrades
the original file/directory in-place.

# Configuration

* <details open>
  
  <summary><h6><code>ask_for_backup</h6></code> (boolean)</summary>
  
  <div>
  
  Whether to prompt the user to back up their file
  every time they would like to upgrade a `.norg` document.
  
  Unless you are certain of what you are doing, it's best to leave
  this set to `true`.
  
  </div>
  
  ```lua
  true
  ```
  
  </details>


# Required Modules

- [`core.fs`](https://github.com/nvim-neorg/neorg/wiki/Filesystem) - A cross-platform set of utilities to traverse filesystems.
- [`core.integrations.treesitter`](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration) - A module designed to integrate Treesitter into Neorg.

