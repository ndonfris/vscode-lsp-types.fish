# vscode-lsp-types.fish

CLI to fetch permalinks for type definitions from the vscode-languageserver npm package

## Installation

### Prerequisites

- [Fish shell](https://fishshell.com/) (version 3.0 or higher recommended)
- [Fisher](https://github.com/jorgebucaran/fisher) - A plugin manager for Fish

### Installing Fisher

If you don't already have Fisher installed, you can install it with:

```fish
curl -sL https://raw.githubusercontent.com/jorgebucaran/fisher/main/functions/fisher.fish | source && fisher install jorgebucaran/fisher
```

### Installing vscode-lsp-types.fish

Once Fisher is installed, you can install this plugin using any of the following methods:

#### Method 1: Install from GitHub (Recommended)

```fish
fisher install ndonfris/vscode-lsp-types.fish
```

#### Method 2: Install from a specific branch or tag

```fish
fisher install ndonfris/vscode-lsp-types.fish@master
```

#### Method 3: Install from a local directory

If you've cloned the repository locally:

```fish
fisher install /path/to/vscode-lsp-types.fish
```

### Verifying Installation

After installation, the plugin's functions should be available in your Fish shell. You can verify the installation by listing your installed Fisher plugins:

```fish
fisher list
```

## Usage

<!-- Add usage instructions here -->

This plugin provides CLI tools to fetch permalinks for type definitions from the vscode-languageserver npm package.

## Updating

To update to the latest version:

```fish
fisher update ndonfris/vscode-lsp-types.fish
```

## Uninstalling

To remove this plugin:

```fish
fisher remove ndonfris/vscode-lsp-types.fish
```

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details. 
