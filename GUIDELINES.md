# Meadow guidelines

These are the rules every Meadow port should follow. The idea is pretty simple: every color has one job, and it does that same job in every app. A keyword in Emacs and a keyword in Neovim should be the same lavender, an error in your terminal should be the same poppy red as an error in your editor. If you stick to the tables below, your port will look like Meadow without you having to think about it too much.

Everything here applies to both Meadow and Meadow Light. Each color keeps the same job, only the hex codes change, and you can find both in [palette.json](palette.json).

## The basics

- Only use colors from the palette. Do not add new ones, and do not lighten, darken or mix them.
- Do not use transparency to fake a color. If an app forces you to use alpha somewhere, pick the tint that is closest to what you need.
- Ship both versions, and call them `meadow` and `meadow-light` (or `Meadow` and `Meadow Light` if the app shows names to people).
- If an app has something these tables do not cover, pick whatever color is closest in meaning and write down what you did in the port's README.

## Ground

The ground colors are the neutrals. In Meadow they go from darkest to lightest, in Meadow Light it is flipped, but each one keeps its job.

| Color | Used for | Meadow | Meadow Light |
|---|---|---|---|
| night | Recessed areas: sidebars, inactive panes, code blocks, the current line | `#17131b` | `#e6e0ed` |
| base | The main background | `#1f1a24` | `#f1ecf7` |
| surface | Raised things: popups, menus, tooltips | `#2a2431` | `#f8f5fc` |
| overlay | Borders, separators, scrollbars, the selected item in a list | `#3a3245` | `#d9d2e2` |
| dim | Line numbers, brackets and punctuation, whitespace markers | `#5f5769` | `#a9a0b4` |
| muted | Comments, placeholders, disabled text | `#958aa3` | `#81778d` |
| subtle | Secondary text: status lines, labels, operators | `#b9b0c6` | `#5c5169` |
| text | Main text and variables | `#ebe7f0` | `#352c3f` |

## Flowers

There are six flowers, and each one comes in three shades:

- `main` is the one you will use most. It is meant for text.
- `soft` is a quieter version, for things that should sit a step back. It is also what the terminal's normal colors use.
- `tint` is for backgrounds only, like diff lines, selections and highlights. Never use a tint for text.

| Flower | Meadow (main / soft / tint) | Meadow Light (main / soft / tint) |
|---|---|---|
| poppy | `#d68583` `#b06a69` `#623b3b` | `#9e4c4d` `#b16968` `#f1d2d1` |
| marigold | `#e9b17c` `#c49365` `#5d4127` | `#925f2a` `#a5794e` `#ecd6c3` |
| sage | `#a4bba9` `#879b8c` `#3a4d3e` | `#536e59` `#6d8472` `#d1dfd4` |
| dew | `#84c7d5` `#6ca6b2` `#1e5059` | `#2d717d` `#518792` `#c1e1e8` |
| cornflower | `#9cb8eb` `#8099c5` `#374866` | `#4b6697` `#667ea9` `#cedbf3` |
| lavender | `#c1b0e7` `#a192c2` `#4c4161` | `#6d5b90` `#8374a3` `#ddd6ef` |

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
| Cursor | lavender main |
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
| 0 | black | `#2a2431` | `#f8f5fc` |
| 1 | red | `#b06a69` | `#b16968` |
| 2 | green | `#879b8c` | `#6d8472` |
| 3 | yellow | `#c49365` | `#a5794e` |
| 4 | blue | `#8099c5` | `#667ea9` |
| 5 | magenta | `#a192c2` | `#8374a3` |
| 6 | cyan | `#6ca6b2` | `#518792` |
| 7 | white | `#b9b0c6` | `#5c5169` |
| 8 | bright black | `#5f5769` | `#a9a0b4` |
| 9 | bright red | `#d68583` | `#9e4c4d` |
| 10 | bright green | `#a4bba9` | `#536e59` |
| 11 | bright yellow | `#e9b17c` | `#925f2a` |
| 12 | bright blue | `#9cb8eb` | `#4b6697` |
| 13 | bright magenta | `#c1b0e7` | `#6d5b90` |
| 14 | bright cyan | `#84c7d5` | `#2d717d` |
| 15 | bright white | `#ebe7f0` | `#352c3f` |

On top of the 16 colors, use base for the background, text for the foreground, lavender main for the cursor and lavender tint for the selection. "Black" and "white" are named after their place in a dark terminal, so in Meadow Light black is the light one and white is the dark one. That is normal for light themes, and it keeps programs that hardcode these colors readable.
