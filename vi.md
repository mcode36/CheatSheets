# Quick Reference

## Starting vi
- create a new file xyz.txt
> vi xyz.txt

## Insert Mode commands
i : insert (on current cursor)
a : insert (after current cursor)
o : insert (under current line)
When in insert mode, press "ESC" will switch to command mode

## Command Mode commands
h,j,k,l : move cursor left,down,up,right
x       : remove one character
dd      : remove current line
yy      : copy current line (into buffer)
p       : paste (from buffer)
:w      : write
:q      : quit
:wq     : write and quit
:w a.txt : save as new file "a.txt"
