# tmux

## Docs

[official doc](http://www.openbsd.org/cgi-bin/man.cgi/OpenBSD-current/man1/tmux.1?query=tmux&sec=1)

[material-copy clipboard](http://foocoder.com/blog/zhong-duan-huan-jing-zhi-tmux.html/)

## Hot Hotkey

could change conf file to set new hotkey. but potentially dangerous cause they may confilct with native hot key or tpm plugin hot key.

**Native hotkey**

```
ctrl-b: # also known as default prefix key
  %, split to right
  ", split to bottom
  x, kill current pane
  o, swap pane
  &, kill current window 
  d, detach current window # you can still restore it by 'tmux attach -t session_id'
       in normal terminal: tmux ls;(list all session). tmux attach -t [session name];(reattach session)
  up/down/left/right, move between panes
  Page Up: scroll inside current pane. enable copy mode
  [  - enter copy mode (then use emacs select/yank keys)
      * press CTRL-SPACE or CTRL-@ to start selecting text
      * move cursor to end of desired text
      * press ALT-w to copy selected text
      * !!![from tmux-yank] y to copy selected text to system clipboard
 ]  - paste copied text  


  c, create a new window for current session. the previous window still is there.
  w, list all windows for current session
  n/p, switch window
  f, search for window
  r, reload configuration
```
**Tpm hotkey**

Hotkey only valid if you already installed corresponding plugin

```
ctrl-b: # also known as default prefix key
  I, install tpm package
  Tab, load directory side view
  ctrl-s, save current layout
  ctrl-r, restore last saved layout
```

## Tmux command

start new:

    tmux

start new with session name:

    tmux new -s myname

attach:

    tmux attach  #  (or at, or attach)

attach to named:

    tmux attach -t myname

list sessions:

    tmux ls

<a name="killSessions"></a>kill session:

    tmux kill-session -t myname

<a name="killAllSessions"></a>Kill all the tmux sessions:

    tmux ls | grep : | cut -d. -f1 | awk '{print substr($1, 0, length($1)-1)}' | xargs kill
