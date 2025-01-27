# pdb-cheatsheet
Most used commands in Python Debugger (PDB).

## How to run Python script with debugger?
* `python -m pdb script.py`

## Most used commands:
    
### HELP
* `help` = show all PDB commands
* `help p` = show help for 'p' command
    
### MOVE
* `n | next` = next line (steps over function)
* `s | step` = next line (step into function)

* `unt | until` = continue execution until next line number (helps to exit loop)
* `r | return` = continue execution current function returns
* `c | continue` = continue execution ltill next breakpoint / or end of script
* `j | jump 10` = set the line 10 as to be executed next
* `u | up` = move 1 frame/level up
* `d | down` = move 1 frame/level down

### CONTEXT
* `w | where` = print all levels/frames
* `a | args` = print arguments of current function
* `l | list` = print source code around current line
  * `l 1,5` = print source code line numbers 1:5
* `ll` = see the source related to the current function or frame

### SHOW VARIABLES
* `x`  = show content of variable 'x'
* `p`  = print variable 'x'
* `pp` = pretty-print variable 'x'

### CUSTOM CODE
* `!x=2` = executes code x=2

### BREAKPOINTS
* `b | break` = show all breakpoints
* `b 150` = set permanent breakpoint to line 150
* `tbreak 150`  = set temporary (one-time) breakpoint to line 150
* `cl | clear`     = clear all breakpoints

Full syntax: `b(reak) [[filename:]lineno | function[, condition]]`

Examples:
* `break 13`  # Set breakpoint on line number 13
* `break divide`  # Set breakpoint on $divide function 
* `break divide, denominator == 0`  # Set breakpoint in $divide function only if denominator is 0

### SPECIAL
* `interact` = start interactive shell in debugger using the globals() and locals() in the current frame

### QUIT
* `q | quit` = quit / abort program




