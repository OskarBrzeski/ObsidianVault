# How to install
## Arch
```bash
sudo pacman -S tmux
```
# How to use
## Outside tmux
Starting a session
```bash
tmux
tmux new
tmux new-session
tmux new -s sessionname  # you can name sessions this way
tmux new-session -A -s sessionanme  # attach to sessionname if exists, else create new session
```
List all sessions
```bash
tmux ls
tmux list-sessions
```
Attach to last session
```bash
tmux a
tmux at
tmux attach
tmux attach-session
```
Attach to specific session
```bash
tmux a -t sessionname
```
Kill session
```bash
tmux kill-ses -t sessionname
tmux kill-session -t sessionname
tmux kill-session -a  # kills all sessions
tmux kill-session -a -t sessionname  # kills all sessions except sessionname
```
List info
```bash
tmux info
```
## Inside tmux
Detach from session
```
ctrl+b d
```
List all sessions
```
ctrl+b s
```

Create new window
```
ctrl+b c
```
List all windows
```
ctrl+b w
```
Move into another window
```
ctrl+b n  # next window
ctrl+b p  # previous window
ctrl+b <num>  # go to window <num>
```
Close window
```
ctrl+b &
```

Split window into panes
```
ctrl+b %  # vertically
ctrl+b "  # horizontally
```
Move to pane
```
ctrl+b <arrow>
ctrl+b o  # move to next pane
ctrl+b q <num>
```
Resize current pane
```
ctrl+b+<arrow>
ctrl+b ctrl+<arrow>
```
Convert current pane into window
```
ctrl+b !
```
Close current pane
```
ctrl+b x
```
# Config files
Local tmux config
```
$XDG_CONFIG_HOME/tmux/tmux.conf  # if set
~/.config/tmux/tmux.conf
```
Global tmux config
```
/etc/tmux.conf
```

Change command prefix
```
unbind C-b  # Ctrl-b
set -g prefix C-a  # Ctrl-a used as example
bind C-a send-prefix
```
