# Meadow guidelines

These are the rules every Meadow port should follow. The idea is pretty simple: every color has one job, and it does that same job in every app. A keyword in Emacs and a keyword in Neovim should be the same lavender, an error in your terminal should be the same poppy red as an error in your editor. If you stick to the tables below, your port will look like Meadow without you having to think about it too much.

Everything here applies to both Meadow and Meadow Light. Each color keeps the same job, only the hex codes change, and you can find both in [palette.json](palette.json).

## The basics

- Only use colors from the palette. Do not add new ones, and do not lighten, darken or mix them.
- Do not use transparency to fake a color. If an app forces you to use alpha somewhere, pick the tint that is closest to what you need.
- Ship both versions, and call them `meadow` and `meadow-light` (or `Meadow` and `Meadow Light` if the app shows names to people).
- Put the port in its own folder under `ports/`, with a short README that explains how to install it. If the app's package manager needs the port to have its own repo (MELPA does, for Emacs), that is fine too, it will just be linked from here instead.
- If an app has something these tables do not cover, pick whatever color is closest in meaning.

## Ground

The ground colors are the neutrals. In Meadow they go from darkest to lightest, in Meadow Light it is flipped, but each one keeps its job.

| Color | Used for | Meadow | Meadow Light |
|---|---|---|---|
| night | Recessed areas: sidebars, inactive panes, code blocks, the current line | `#17131b` | `#efdee4` |
| base | The main background | `#1f1a24` | `#f7e8ee` |
| surface | Raised things: popups, menus, tooltips | `#2a2431` | `#fbf1f5` |
| overlay | Borders, separators, scrollbars, the selected item in a list | `#3a3245` | `#e1ced7` |
| dim | Line numbers, brackets and punctuation, whitespace markers | `#5f5769` | `#ab98a5` |
| muted | Comments, placeholders, disabled text | `#958aa3` | `#857284` |
| subtle | Secondary text: status lines, labels, operators | `#b9b0c6` | `#5f4e63` |
| text | Main text and variables | `#ebe7f0` | `#382a3d` |

## Flowers

There are six flowers, and each one comes in three shades:

- `main` is the one you will use most. It is meant for text.
- `soft` is a quieter version, for things that should sit a step back. It is also what the terminal's normal colors use.
- `tint` is for backgrounds only, like diff lines, selections and highlights. Never use a tint for text.

| Flower | Meadow (main / soft / tint) | Meadow Light (main / soft / tint) |
|---|---|---|
| poppy | `#d68583` `#b06a69` `#623b3b` | `#b9454c` `#c86265` `#f8d4d3` |
| marigold | `#e9b17c` `#c49365` `#5d4127` | `#b76316` `#c57b3d` `#f6dac2` |
| sage | `#a4bba9` `#879b8c` `#3a4d3e` | `#507357` `#6b8970` `#d0e2d3` |
| dew | `#84c7d5` `#6ca6b2` `#1e5059` | `#217584` `#4c8b98` `#bfe4ec` |
| cornflower | `#9cb8eb` `#8099c5` `#374866` | `#4a68a0` `#6680b1` `#ceddf8` |
| lavender | `#c1b0e7` `#a192c2` `#4c4161` | `#715c97` `#8775aa` `#e0d7f4` |

Poppy, marigold and sage double as the status colors (error, warning and success). That is on purpose, so try to not use them for anything that could be mistaken for a status.

## Code

| What | Color |
|---|---|
| Keywords (`if`, `let`, `defun`, `return`) | lavender main |
| Builtins | lavender soft |
| Function names, both definitions and calls | cornflower main |
| Macros, decorators, preprocessor | cornflower soft |
| Strings | sage main |
| Docstrings | sage main, italic |
| Numbers, constants, booleans | marigold main |
| Escape sequences, regex | marigold soft |
| Types and classes | dew main |
| Properties and fields | dew soft |
| Variables and parameters | text |
| Operators | subtle |
| Brackets and punctuation | dim |
| Comments | muted, italic |

## Status and diffs

| What | Text | Background (if the app has one) |
|---|---|---|
| Error | poppy main | poppy tint |
| Warning | marigold main | marigold tint |
| Info, hints | dew main | dew tint |
| Success | sage main | sage tint |
| Diff: added | sage main | sage tint |
| Diff: removed | poppy main | poppy tint |
| Diff: changed | marigold main | marigold tint |

## Interface

| What | Color |
|---|---|
| Cursor | text, with base for the character under it |
| Current line | night background |
| Selection | lavender tint background, text keeps its own colors |
| Search matches | marigold tint background |
| Current search match | marigold main background, base text |
| Matching bracket | lavender main, overlay background |
| Links | lavender main |
| Focused borders, active tab marker | lavender main |
| Inactive borders | overlay |

## Writing and markup

This covers Markdown, Org, and anything similar.

| What | Color |
|---|---|
| Heading 1 | lavender main |
| Heading 2 | cornflower main |
| Heading 3 | dew main |
| Heading 4 and below | sage main |
| Inline code | lavender main on surface |
| Code blocks | night background |
| Links | lavender main |
| Quotes | subtle, italic |
| List markers | dim |
| Bold and italic text | text, only the weight or slant changes |

## Font weight and italics

Keep everything at regular weight by default and let the colors do the work. The only exception is bold text in markup, since the writer actually asked for it there.

Italics are used for comments and docstrings only (and quotes in markup). If the app lets you, give people a way to turn italics off, not every font has a nice italic and some people just do not like them.

## Terminal

| # | Color | Meadow | Meadow Light |
|---|---|---|---|
| 0 | black | `#2a2431` | `#fbf1f5` |
| 1 | red | `#b06a69` | `#c86265` |
| 2 | green | `#879b8c` | `#6b8970` |
| 3 | yellow | `#c49365` | `#c57b3d` |
| 4 | blue | `#8099c5` | `#6680b1` |
| 5 | magenta | `#a192c2` | `#8775aa` |
| 6 | cyan | `#6ca6b2` | `#4c8b98` |
| 7 | white | `#b9b0c6` | `#5f4e63` |
| 8 | bright black | `#5f5769` | `#ab98a5` |
| 9 | bright red | `#d68583` | `#b9454c` |
| 10 | bright green | `#a4bba9` | `#507357` |
| 11 | bright yellow | `#e9b17c` | `#b76316` |
| 12 | bright blue | `#9cb8eb` | `#4a68a0` |
| 13 | bright magenta | `#c1b0e7` | `#715c97` |
| 14 | bright cyan | `#84c7d5` | `#217584` |
| 15 | bright white | `#ebe7f0` | `#382a3d` |

On top of the 16 colors, use base for the background, text for the foreground, text for the cursor (with base for the character under it) and lavender tint for the selection. "Black" and "white" are named after their place in a dark terminal, so in Meadow Light black is the light one and white is the dark one. That is normal for light themes, and it keeps programs that hardcode these colors readable.
