# Pyret VSCode Theme

A VS Code extension that provides syntax highlighting and color themes for the [Pyret programming language](https://www.pyret.org/) (`.arr` files).

This extension uses the **real Pyret tokenizer** (the same one used by [code.pyret.org](https://code.pyret.org)) via VS Code's Semantic Tokens API, ensuring accurate and context-aware highlighting.

## Included Themes

- ☀️ **Pyret Light** — clean white background with official colors from `code.pyret.org`
- 🌙 **Pyret Dark (One Dark)** — sleek dark mode based on Atom's popular **One Dark Pro** palette (`#282c34`)

## Features

- 🔤 **Accurate syntax highlighting** via the actual Pyret tokenizer (not just regexes)
- 🟪 **Keywords** (`fun`, `check`, `ask`, `end`, `if`, `else`, `cases`, `data`, etc.)
- 🟦 **Function names & calls**
- 🟨 **Types & data variants**
- 🟩 **Strings**
- 🩶 **Comments** (`# ...` and `#| ... |#`)
- 🟧 **Numbers & Booleans**
- ⬜ **Variables & Parameters**

## Color Mapping Comparison

| Token Type | Pyret Light | Pyret Dark (One Dark) |
|------------|-------------|-----------------------|
| Keywords (`fun`, `check`, `end`, ...) | `#b91c1c` (Crimson) | `#c678dd` (Purple/Magenta) |
| Functions & Calls | `#0066cc` (Blue) | `#61afef` (Bright Blue) |
| Types (`List`, `String`, `Number`, ...) | `#5b21b6` (Dark Purple) | `#e5c07b` (Gold/Yellow) |
| Strings | `#16a34a` (Green) | `#98c379` (Light Green) |
| Comments | `#d97706` (Orange) | `#7f848e` (Gray Italic) |
| Numbers & Booleans | `#1d4ed8` (Dark Blue) | `#d19a66` (Orange) |
| Parameters | `#111827` (Dark Graphite) | `#e06c75` (Coral Red) |
| Variables & Operators | `#111827` (Dark Graphite) | `#56b6c2` (Cyan) / `#abb2bf` |

## Installation

### From VSIX file
```bash
code --install-extension pyret-vscode-theme-1.1.0.vsix
```

### Selecting your theme
1. Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on macOS)
2. Select **"Preferences: Color Theme"**
3. Choose either **"Pyret Light"** or **"Pyret Dark (One Dark)"**

## How it works

The extension embeds a copy of the Pyret CodeMirror tokenizer (`pyret.js`) and adapts it to run in Node.js using a custom CodeMirror Stream emulator. It registers a `DocumentSemanticTokensProvider` that tokenizes each file using the real Pyret parser state machine, producing accurate token classification that regex-based TextMate grammars cannot achieve.

## License

MIT

## Credits

- Pyret language tokenizer from [pyret-codemirror-mode](https://github.com/brownplt/pyret-codemirror-mode) by the [Pyret team](https://www.pyret.org/) (Brown University PLT)
- One Dark Pro color palette by [Atom / Binaryify](https://github.com/Binaryify/OneDark-Pro)
