# Pyret Light Theme

A VS Code extension that provides syntax highlighting and a color theme for the [Pyret programming language](https://www.pyret.org/) (`.arr` files).

This extension uses the **real Pyret tokenizer** (the same one used by [code.pyret.org](https://code.pyret.org)) via VS Code's Semantic Tokens API, ensuring accurate and context-aware highlighting.

## Features

- 🎨 **Pyret Light color theme** — clean white background with carefully chosen colors from the official `code.pyret.org` theme
- 🔤 **Accurate syntax highlighting** via the actual Pyret tokenizer (not just regexes)
- 🟥 **Keywords** (`fun`, `check`, `ask`, `end`, `if`, `else`, `cases`, `data`, etc.) — Crimson Red
- 🟦 **Function names & calls** — Blue
- 🟪 **Types & data variants** — Purple
- 🟩 **Strings** — Green
- 🟠 **Comments** (`# ...` and `#| ... |#`) — Orange/Gold
- 🔵 **Numbers** (decimal, rational `1/3`, rough `~1.5`) — Blue shades
- ⬛ **Variables** — Dark Graphite

## Installation

### From VS Code Marketplace
1. Open VS Code
2. Go to Extensions (`Ctrl+Shift+X`)
3. Search for **"Pyret Light Theme"**
4. Click **Install**

### From VSIX file
```bash
code --install-extension pyret-light-theme.vsix
```

### Apply the color theme
1. `Ctrl+Shift+P` → **"Color Theme"** → select **"Pyret Light"**

## Screenshot

Files with `.arr` extension are automatically recognized as Pyret and highlighted.

## Token Colors

| Token | Color |
|-------|-------|
| Keywords (`fun`, `check`, `end`, ...) | `#b91c1c` (Crimson Red) |
| Function names & calls | `#0066cc` (Blue) |
| Types & data variants | `#5b21b6` (Purple) |
| Strings | `#16a34a` (Green) |
| Comments | `#d97706` (Orange/Gold) |
| Numbers (decimal) | `#1d4ed8` (Dark Blue) |
| Numbers (rational `1/3`) | `#4f46e5` (Indigo) |
| Numbers (rough `~1.5`) | `#2563eb` (Blue) |
| Booleans (`true`, `false`) | `#2563eb` (Blue) |
| Variables | `#111827` (Dark Graphite) |

## How it works

The extension embeds a copy of the Pyret CodeMirror tokenizer (`pyret.js`) and adapts it to run in Node.js using a custom CodeMirror Stream emulator. It registers a `DocumentSemanticTokensProvider` that tokenizes each file using the real Pyret parser state machine, producing accurate token classification that regex-based TextMate grammars cannot achieve.

## License

MIT

## Credits

- Pyret language tokenizer from [pyret-codemirror-mode](https://github.com/brownplt/pyret-codemirror-mode) by the [Pyret team](https://www.pyret.org/) (Brown University PLT)
- Color palette from the [code.pyret.org](https://github.com/brownplt/code.pyret.org) pyret-light theme
