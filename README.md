# Vim Cheatsheet

>Disclaimer: This cheatsheet is summarized from personal experience and other online tutorials. It should not be considered as an official advice.

## Global
```bash
:help keyword # open help for keyword
:o file       # open file
:saveas file  # save file as
:close        # close current pane
```

## Cursor movement
```bash
h        # move cursor left, left of the bump on the keyboard
j        # move cursor down, opposite of jumping
k        # move cursor up, kick someone, they go down
l        # move cursor right, is right even tho its left 
H        # move to top of screen, HOP to the TOP
M        # move to middle of screen, M iddle
L        # move to bottom of screen, L ow
w        # jump forwards to the start of a word, word!
W        # jump forwards to the start of a word (words can contain punctuation), Word after . is capital
e        # jump forwards to the end of a word, e like end
E        # jump forwards to the end of a word (words can contain punctuation), End efter . is capital 
b        # jump backwards to the start of a word, beginning
B        # jump backwards to the start of a word (words can contain punctuation), Beginning after . is capital
0        # jump to the start of the line, programmers start to count at 0
^        # jump to the first non-blank character of the line, ^ is before the 1 on the keyboard 
$        # jump to the end of the line, in the end: payout $
g_       # jump to the last non-blank character of the line, g (eee) I forgot something
gg       # go to the first line of the document, go, go! quickly to the top!
G        # go to the last line of the document, Go to the end 
5G       # go to line 5
fx       # jump to next occurrence of character x, find x
tx       # jump to before next occurrence of character x, traverse x
}        # jump to next paragraph (or function/block, when editing code), wrap it!
{        # jump to previous paragraph (or function/block, when editing code), begin of wrap
zz       # center cursor on screen, zzzooom to the middle 

## Insert mode - inserting/appending text
```bash
i        # insert before the cursor, insert here!
I        # insert at the beginning of the line,  I want you to insert.
a        # insert (append) after the cursor, append 
A        # insert (append) at the end of the line, At first append
o        # append (open) a new line below the current line, of course theres more
O        # append (open) a new line above the current line, Oh I forgot!
ea       # insert (append) at the end of the word, easy append
Esc      # exit insert mode, Escape
```

## Editing
```bash
r        # replace a single character, r like replace
J        # join line below to the current one, Join 
cc       # change (replace) entire line, adding your boss cc requires changes
cw       # change (replace) to the start of the next word, change until word 
ce       # change (replace) to the end of the next word, change until end of word 
cb       # change (replace) to the start of the previous word, change until beginning
c0       # change (replace) to the start of the line, change until 0 
c$       # change (replace) to the end of the line, change undil $ 
s        # delete character and substitute text, substitute this
S        # delete line and substitute text (same as cc), Sssssssss.... booom!
xp       # transpose two letters (delete and paste), 
.        # repeat last command
u        # undo
Ctrl + r # redo
```

## Marking text (visual mode)
```bash
v        # start visual mode, mark lines, then do a command (like y-yank)
V        # start linewise visual mode
o        # move to other end of marked area
O        # move to other corner of block
aw       # mark a word
ab       # a block with ()
aB       # a block with {}
ib       # inner block with ()
iB       # inner block with {}
Esc      # exit visual mode
Ctrl + v # start visual block mode
```

## Visual commands
```bash
>       # shift text right
<       # shift text left
y       # yank (copy) marked text
d       # delete marked text
~       # switch case
```

## Cut and paste
```bash
yy       # yank (copy) a line
2yy      # yank (copy) 2 lines
yw       # yank (copy) the characters of the word from the cursor position to the start of the next word
y$       # yank (copy) to end of line
p        # put (paste) the clipboard after cursor
P        # put (paste) before cursor
dd       # delete (cut) a line
2dd      # delete (cut) 2 lines
dw       # delete (cut) the characters of the word from the cursor position to the start of the next word
D        # delete (cut) to the end of the line
d$       # delete (cut) to the end of the line
d^       # delete (cut) to the first non-blank character of the line
d0       # delete (cut) to the begining of the line
x        # delete (cut) character
```

## Search and replace
```bash
/pattern       # search for pattern
?pattern       # search backward for pattern
\vpattern      # 'very magic' pattern: non-alphanumeric characters are interpreted as special regex symbols (no escaping needed)
n              # repeat search in same direction
N              # repeat search in opposite direction
:%s/old/new/g  # replace all old with new throughout file
:%s/old/new/gc # replace all old with new throughout file with confirmations
:noh           # remove highlighting of search matches
```

## Search in multiple files
```bash
:vimgrep /pattern/ {file} # search for pattern in multiple files
:cn                       # jump to the next match
:cp                       # jump to the previous match
:copen                    # open a window containing the list of matches
```

## Exiting
```bash
:w              # write (save) the file, but don't exit
:w !sudo tee %  # write out the current file using sudo
:wq or :x or ZZ # write (save) and quit
:q              # quit (fails if there are unsaved changes)
:q! or ZQ       # quit and throw away unsaved changes
```

## Working with multiple files
```bash
:e file       # edit a file in a new buffer
:bnext or :bn # go to the next buffer
:bprev or :bp # go to the previous buffer
:bd           # delete a buffer (close a file)
:ls           # list all open buffers
:sp file      # open a file in a new buffer and split window
:vsp file     # open a file in a new buffer and vertically split window
Ctrl + ws     # split window
Ctrl + ww     # switch windows
Ctrl + wq     # quit a window
Ctrl + wv     # split window vertically
Ctrl + wh     # move cursor to the left window (vertical split)
Ctrl + wl     # move cursor to the right window (vertical split)
Ctrl + wj     # move cursor to the window below (horizontal split)
Ctrl + wk     # move cursor to the window above (horizontal split)
```

## Tabs
```bash
:tabnew or :tabnew file # open a file in a new tab
Ctrl + wT               # move the current split window into its own tab
gt or :tabnext or :tabn # move to the next tab
gT or :tabprev or :tabp # move to the previous tab
<number>gt              # move to tab <number>
:tabmove <number>       # move current tab to the <number>th position (indexed from 0)
:tabclose or :tabc      # close the current tab and all its windows
:tabonly or :tabo       # close all tabs except for the current one
:tabdo command          # run the command on all tabs (e.g. :tabdo q - closes all opened tabs)
```
