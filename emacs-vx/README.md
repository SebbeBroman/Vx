# vx-mode for Emacs

A major mode for editing `.vx` files. It gives you:

- Syntax highlighting for keywords, types, numbers, strings, `name!` macro calls,
  `$var` macro variables, and the names in `fn`, `struct`, `let` and `macro_rules`.
- `//` comments, with `///` doc comments shown in the doc-comment face.
- Indentation that matches `vx-format`: 2 spaces for each open `{`.
- An `imenu` index of functions, types and macros.

## Install

Add this to your Emacs init file:

```elisp
(add-to-list 'load-path "/path/to/Vx/emacs-vx")
(require 'vx-mode)
```

`.vx` files then open in `vx-mode`. To use a different indent width, set
`vx-indent-offset`.

## Tests

Run from the repository root:

```sh
emacs --batch -L emacs-vx -l emacs-vx/vx-mode-tests.el -f ert-run-tests-batch-and-exit
```

The keyword lists in `vx-mode.el` come from `src/lexer.rs`. When the lexer
gets a new keyword, add it to `vx-keywords` too.
