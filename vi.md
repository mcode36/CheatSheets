# Quick Reference

## Starting vi
- create a new file xyz.txt
> vi xyz.txt

## Insert Mode commands
- i : insert (on current cursor)
- a : insert (after current cursor)
- o : insert (under current line)
- When in insert mode, press "ESC" will switch to command mode

## Command Mode commands
- h,j,k,l : move cursor left,down,up,right (same as using arrow keys)
- x       : remove one character
- u       : undo
- dd      : remove current line
- :w      : write
- :q      : quit
- :q!     : quit without save (ignore all changes)
- :wq     : write and quit
- :w a.txt : save as new file "a.txt"

## Command Mode commands : Advanced
- /www    : search the string "www"
- yy      : copy current line (into buffer)
- p       : paste (from buffer)
- n       : move to next search result
