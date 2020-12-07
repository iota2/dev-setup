# iota2

> Making Imaginations, Real

<i2.iotasquare@gmail.com>

```
 ██╗ ██████╗ ████████╗ █████╗ ██████╗
 ██║██╔═══██╗╚══██╔══╝██╔══██╗╚════██╗
 ██║██║   ██║   ██║   ███████║ █████╔╝
 ██║██║   ██║   ██║   ██╔══██║██╔═══╝
 ██║╚██████╔╝   ██║   ██║  ██║███████╗
 ╚═╝ ╚═════╝    ╚═╝   ╚═╝  ╚═╝╚══════╝
```

[![BSD licensed](https://img.shields.io/badge/license-GPL3-blue.svg)](https://raw.githubusercontent.com/iota2/dev-setup/master/LICENSE)


# VIM Cheat Sheet

### INSERT Mode
Command         | Description
:---:           | :---
<kbd>i</kbd>    | Insert at the cursor
<kbd>a</kbd>    | Insert after the cursor
<kbd>A</kbd>    | [APPEND] Insert at the end of line
<kbd>o</kbd>    | Insert a new line after the current one
<kbd>O</kbd>    | Insert a new line before the current one

### CONTROL Commands
Command	          | Description
:---:             | :---
`:w`              | Save the file
`:q`              | Quit and exit the file
`:wq`             | Save and exit the file
`q!`              | Exit without saving
`:saveas <path>`  | Save the file to `<path>`

### MOVE across Columns
Command               | Description
:---:                 | :---
`<n>` <kbd>h</kbd>    | Equivalent to arrow move left [for `n` number of moves]
`<n>` <kbd>j</kbd>    | Equivalent to arrow move down [for `n` number of moves]
`<n>` <kbd>k</kbd>    | Equivalent to arrow move up [for `n` number of moves]
`<n>` <kbd>l</kbd>    | Equivalent to arrow move right [for `n` number of moves]
<kbd>O</kbd>          | Goto first column / beginning of line
<kbd>^</kbd>          | Goto first non-blank character of line
<kbd>$</kbd>          | Goto the end of line
<kbd>g_</kbd>         | Goto last non-blank character of line

### MOVE across line
Command         | Description
:---:           | :---
<kbd>f</kbd>`a` | Goto next occurrence of character `a` in current line
<kbd>t</kbd>`a` | Go before next occurrence of character `a` in current line
<kbd>,</kbd>    | Goto NEXT occurrence of result of <kbd>f</kbd> / <kbd>t</kbd>
<kbd>;</kbd>    | Goto PREVIOUS result from <kbd>f</kbd> / <kbd>t</kbd>


### MOVE across word/WORD
> words are composed of letters and underscore character. lets call a WORD, a
> group of letters separated by blank characters

Command         | Description
:---:           | :---
<kbd>w</kbd>    | Goto start of next word
<kbd>W</kbd>    | Goto start of next WORD
<kbd>e</kbd>    | Goto end of current word
<kbd>E</kbd>    | Goto end of current WORD
<kbd>*</kbd>    | Goto NEXT occurrence of word under cursor
<kbd>#</kbd>    | Goto PREVIOUS occurrence of word under cursor

### MOVE across file
Command                           | Description
:---:                             | :---
`<n>` <kbd>G</kbd>                | Goto line number `n`
<kbd>G</kbd>                      | Goto last line for the file
<kbd>gg</kbd>                     | Goto start of the file [Equivalent to `1G`]
[<kbd>ctrl</kbd> + <kbd>a</kbd>]  | Increment the number at cursor
`<n>` <kbd>></kbd>                | Indent Right `n` number of times
`<n>` <kbd><</kbd>                | Indent left `n` number of times
[<kbd>ctrl</kbd> + <kbd>n</kbd>]  | Auto complete text

### CUT-COPY-PASTE
Command                               | Description
:---:                                 | :---
`<n>` <kbd>d</kbd>                    | delete `n` characters
`<n>` <kbd>y</kbd>                    | Yank / Copy `n` characters
<kbd>p</kbd>                          | Paste
`<n>` <kbd>dd</kbd>                   | Delete & copy `n` line including current
`<n>` <kbd>yy</kbd>                   | Copy `n` lines including current
`<n>` <kbd>u</kbd>                  	| UNDO `n` number of times
`<n>` [<kbd>ctrl</kbd>+<kbd>r</kbd>]  | REDO `n` number of times

### SEARCH
Command                           | Description
:---:                             | :---
<kbd>/pattern</kbd>               | Search for occurrence of `pattern` in file
<kbd>n</kbd>                      | Goto NEXT occurrence o searched pattern
[<kbd>shift</kbd> + <kbd>n</kbd>] | Goto PREVIOUS occurrence of searched pattern

### COMBINATIONS
```
<start_position> <command> <end_position>
```
**Examples:**
1. `Oy$`
    * `O` : Goto beginning of current line
    * `y` : Yank from here
    * `$` : Up-to end of current line
2. `ye` : Yank from here to end of the word
3. `y2/foo` : Yank up-to 2nd occurrence of `foo`
4. `dt"` : Remove everything until `"`

> What was true for yank <kbd>y</kbd>, is also true for othe commands like
> delete <kbd>d</kbd>, visual select <kbd>v</kbd>, uppercase <kbd>gU</kbd>,
> lowercase <kbd>gu</kbd> etc.

### ZONE Selection
```
<action> a <object>
<action> i <object>
```
> Action can be delete <kbd>d</kbd>, yank <kbd>y</kbd>, or visual <kbd>v</kbd>.
> And an object can be `word`, extended `WORD`, sentence `S`, paragraph `p` or
> natural characters like `"` `'` `)` `}` `]`.

**Example:**
Suppose the cursor is at first `o` of the following line:
```
(map (+) ("foo"))
```
Command     | Selected outcome
:---:       | :---:
`vi"`       | `foo`
`va"`       | `"foo"`
`vi)`       | `"foo"`
`va)`       | `("foo")`
`v2i)`      | `map (+) ("foo")`
`v2a)`      | `(map (+) ("foo"))`

### BLOCK Selection
**Enter Visual-Mode:** [<kbd>ctrl</kbd> + <kbd>v</kbd>]

**Examples:**
1. Write at beginning of selected block (lines):
`^` [<kbd>ctrl</kbd> + <kbd>v</kbd>] `9` [<kbd>ctrl</kbd> + <kbd>d</kbd>]
`I` `>` <kbd>ESC</kbd>
    * `^` : Goto first non-blank character of line.
    * [<kbd>ctrl</kbd> + <kbd>v</kbd>] : Start block selection.
    * `9` [<kbd>ctrl</kbd> + <kbd>d</kbd>] : Move down 9 lines.
    * `I` : Enter insert mode.
    * `>` : Write character `>` at cursor (beginning of line).
    * <kbd>ESC</kbd> : Exit insert mode, writing `>` to all selected lines.

2. Write at end of selected lines:
[<kbd>ctrl</kbd> + <kbd>v</kbd>] `9` [<kbd>ctrl</kbd> + <kbd>d</kbd>]
`$` `A` `,` <kbd>ESC</kbd>
    * [<kbd>ctrl</kbd> + <kbd>v</kbd>] : Start block selection.
    * `9` [<kbd>ctrl</kbd> + <kbd>d</kbd>] : Move down 9 lines.
    * `$` : Goto end of the line.
    * `A` : Enter append mode.
    * `,` : Write text `,` at cursor (End of line).
    * <kbd>ESC</kbd> : Exit append mode, writing `,` to all selected lines.

# License
> `GNU GPU v3` <br>
> This program is free software; you can redistribute it and/or
> modify it under the terms of the GNU General Public License
> as published by the Free Software Foundation; either version 3
> of the License, or (at your option) any later version.
> This program is distributed in the hope that it will be useful,
> but WITHOUT ANY WARRANTY; without even the implied warranty of
> MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
> GNU General Public License for more details.

**Free Software, Hell Yeah!**

