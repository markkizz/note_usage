# Command line usages
## useful CLI

* `xdg-open` - open
* `start  {filename}` - open file
* `clear` - clear terminal
* `ls` - list files
* `cd {directory name}` - change directory
  * `cd / ` - go to root (top) directory
  * `cd ~ ` - go to user home directory
  * `cd .. ` - go up a level
* `mkdir {file name}` - make a directory
* `touch {filename}` - create an empty file
* `rm {filename} ` - remove a file
  * `rm -r {directory name}` - remove a directory and all files within
  * `rm -rf {file}` -force remove
* `mv {filename} {new filename}` - rename a file or folder
* `{command} --help` - for manual
* `cd {2 alph that you want dirrectory} TAB - autocomplete
----------------------------------------
## ex CLI

* `howdoi -c {search how to}` - search in stackoverflow, {--c} highlight
* `tldr {command}` - commandline easy manual

![fdterm](\Coding\book\fdterm.jpg)

* `!{any command}`  - use the previous command
* `{any command} !!` - use the previous flag or command
* `history` - show the command history
* `ls -alh` = a-all, l-long, h-human can read
    - `drwxrwxrwx   1   {athu}  {user}  {file size} {curent interactive} file` - d-diractory, r-read, w-write, x-excte
*  `ctrl-a` - for go to a first line, `ctrl-e` - go to the end of the line , `ctrl-u` - wipe out entire line
* `ctrl-r`
-----------------------------------------
## Tmux
(when you source tmux. you should use tmux perfix)
* tmux conf show: `tmux show -g > ~/.tmux.conf`
* tmux kill session: `tmux kill-session`
flag> kill all `-a`
* tmux for error: `tmux show -g | sed 's/^/set -g /' > ~/.tmux.conf`
* tmux blind key C-a:
`tmux source ~/.tmux.conf`,
`tmux set -g prefix C-a`
* tmux pane window: hit prefix(ctrl-b) and
```
%  horizontal split
"  vertical split

o  swap panes
q  show pane numbers
x  kill pane
⍽  space - toggle between layouts
```
