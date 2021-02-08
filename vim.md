# Vim

![vim commands](https://ibb.co/xmDxN2c)

There’s command mode (“:” starting commands like “:q”) and normal mode, more like shortcuts (like ZZ which is “:wq” shortcut).

Buffer refers a file in memory being editing in vim.

## Useful commands

- :q - quit if no changes were made
- :x - save and quit, will save only if changes were made
- :w - write
- :e - edit
- :buffers, :ls - list buffers
- :bn, :bp - move to next, previous buffer
- ! - append this will force the command

## Useful shortcuts

- w - go to the next word
- b - go to previous word
- r - replace mode
- a - insert mode after current position
- x - delete current position character
- u - undo
- ctrl + r - redo
- s - substitute (delete current position character and enters insert mode)
- 0 - go to beginning of current line
- $ - go to end of current line
- yy - yank (copy)
- pp - paste
- o - create new empty line and enters insert mode
- cc - change current line
- G - go to end of file
- gg - go to beginning of file
- Note: yy, dd and cc could be mixed with w, l and $.

## Split

- :sp - create a horizontal split
- :vsp - create a vertical split
- <int>sp or vsp - create a split with defined height
- :q - closes the split
