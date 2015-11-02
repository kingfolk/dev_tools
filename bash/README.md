# bash tool

## git-prompt.sh

add git branch to bash or other prompt.

**UBUNTU**: download script to `~` and add following lines to .bashrc or its sub folder
```sh
source ~/.git-prompt.sh
PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[01;31m\]$(__git_ps1)\[\033[00m\]\$ '
```

## tmux_cheatsheet.md

a tmux cheatsheet.

## .tmux.conf

tmux configuration file. put it to `~` dir.
