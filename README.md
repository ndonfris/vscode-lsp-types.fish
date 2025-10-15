# vscode-lsp-types.fish

> A Fish shell plugin that generates GitHub permalinks to type definitions in the [vscode-languageserver-node](https://github.com/microsoft/vscode-languageserver-node) repository.

![demo.gif](./demo.gif)

Quickly lookup and link to LSP type definitions from Microsoft's Language Server Protocol implementation. Perfect for documentation, issues, discussions, or when you need to reference specific types in the vscode-languageserver-node package.

## Features

- 🔗 Generate permanent GitHub links to type definitions
- 🎯 Support for interfaces, types, classes, enums, and namespaces
- 📋 Auto-copy links to clipboard
- 🌐 Open links directly in your browser
- 🔍 Search for properties within types (e.g., `CompletionItem.label`)
- ⚡ Smart tab completions for type names and properties
- 🎨 Convenient `vsc` abbreviation

## Installation

### Using [Fisher](https://github.com/jorgebucaran/fisher)

```fish
fisher install ndonfris/vscode-lsp-types.fish
```

### Using [Reef](https://github.com/danielb2/reef)

```fish
reef add ndonfris/vscode-lsp-types.fish
```

### Manual Installation

```fish
# Step 1: Download to your fish config directory
curl -sL https://raw.githubusercontent.com/ndonfris/vscode-lsp-types.fish/main/conf.d/vscode-lsp-types.fish \
  -o ~/.config/fish/conf.d/vscode-lsp-types.fish

# Step 2: Source the script in your config.fish to load on startup
source ~/.config/fish/conf.d/vscode-lsp-types.fish
```

## Requirements

- [Fish shell](https://fishshell.com/) 4.0+
- [GitHub CLI (`gh`)](https://cli.github.com/) - authenticated with GitHub
- [gh-permalink](https://github.com/mislav/gh-permalink) - GitHub CLI extension for generating permalinks
  ```fish
  gh extension install mislav/gh-permalink
  ```

## Usage

### Basic Usage

Generate a permalink to a type definition:

```fish
vscode-lsp-types CompletionItem
# Output: open https://github.com/microsoft/vscode-languageserver-node/blob/<commit-sha>/types/src/main.ts#L123
# Link is automatically copied to clipboard
```

### Property Lookup

Look up specific properties within a type:

```fish
vscode-lsp-types LocationLink.targetUri
# Generates permalink directly to the targetUri property
```

### Options

```
-i, --interface   Search only for interfaces
-t, --type        Search only for type aliases
-c, --class       Search only for classes
-e, --enum        Search only for enums
-n, --namespace   Search only for namespaces
-o, --open        Open the permalink in the browser
    --no-copy     Don't copy the permalink to clipboard
-h, --help        Show help message
```

### Examples

Search for a specific interface:
```fish
vscode-lsp-types --interface Hover
```

Open a type definition in your browser:
```fish
vscode-lsp-types -t Range --open
```

Get a link without copying to clipboard:
```fish
vscode-lsp-types Position --no-copy
```

Use the convenient abbreviation:
```fish
vsc CompletionItem
```

### Tab Completions

The plugin provides intelligent tab completions:

- Type names auto-complete from the actual vscode-languageserver-node repository
- Property names auto-complete when using dot notation (e.g., `CompletionItem.<TAB>`)
- Completions are cached for one hour to minimize API calls

## How It Works

The plugin fetches the latest commit SHA from the `microsoft/vscode-languageserver-node` repository, searches the `types/src/main.ts` file for the requested type definition, and generates a permanent GitHub link to the exact line number. Links remain valid even as the repository evolves because they reference specific commits.

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests on [GitHub](https://github.com/ndonfris/vscode-lsp-types.fish).

### Development

To test changes locally:

1. Fork and clone the repository
2. Make your changes to `conf.d/vscode-lsp-types.fish`
3. Source the file in your shell: `source conf.d/vscode-lsp-types.fish`
4. Test the function: `vscode-lsp-types --help`

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Built for the [Fish shell](https://fishshell.com/)
- Uses the [GitHub CLI](https://cli.github.com/) for API access
- References the [vscode-languageserver-node](https://github.com/microsoft/vscode-languageserver-node) repository by Microsoft

## Related Projects

- [vscode-languageserver-node](https://github.com/microsoft/vscode-languageserver-node) - Microsoft's Language Server Protocol implementation for VS Code
- [fish-shell](https://github.com/fish-shell/fish-shell) - The friendly interactive shell
- [fish-lsp](https://gihtub.com/ndonfris/fish-lsp) - The language-server for fish-shell

---

Made with ❤️ for the Fish shell community
