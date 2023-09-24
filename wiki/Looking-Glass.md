<div align="center">

# `core.looking-glass`

### Code Blocks + Superpowers

The `core.looking-glass` module magnifies code blocks and allows you to edit them in a separate buffer.

![module-showcase](https://user-images.githubusercontent.com/76052559/216782314-5d82907f-ea6c-44f9-9bd8-1675f1849358.gif)

</div>

# Overview

The looking glass module provides a simple way to edit code blocks in an external buffer,
which allows LSPs and other language-specific tools to kick in.

The magnify command can be accessed by running `:Neorg keybind all
core.looking-glass.magnify-code-block` with your cursor underneath the code
block you would like to magnify - it is not bound to any key as of currently,
but you may map it yourself via the [`core.keybinds`](https://github.com/nvim-neorg/neorg/wiki/User-Keybinds) module.

# Configuration

This module provides no configuration options!

# Required Modules

- [`core.integrations.treesitter`](https://github.com/nvim-neorg/neorg/wiki/Treesitter-Integration) - A module designed to integrate Treesitter into Neorg.
- [`core.ui`](https://github.com/nvim-neorg/neorg/wiki/Core-UI) - A set of public functions to help developers create and manage UI (selection popups, prompts...) in their modules.

