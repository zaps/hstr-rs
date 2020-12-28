# hstr-rs

![build status](https://github.com/adder46/hstr-rs/workflows/CI/badge.svg) [![codecov](https://codecov.io/gh/adder46/hstr-rs/branch/master/graph/badge.svg?token=0BZM100XU5)](https://codecov.io/gh/adder46/hstr-rs)

**hstr-rs** is shell history suggest box. Like hstr, but with pages.

It was initially made for bash, but it supports zsh and ksh, too. If you want to use it with tcsh, make sure tcsh saves its history to `~/.tcsh_history`.
​
## Installation
​
Make sure you have ncurses packages installed.
​
```
sudo apt install libncurses5 libncurses5-dev libncursesw5 libncursesw5-dev
```
​
Then run:
​
```
cargo install --git https://github.com/adder46/hstr-rs.git
```
​
If on bash, add this to .bashrc:

```bash
# append new history items to .bash_history
shopt -s histappend 
# don't put duplicate lines or lines starting with space in the history
HISTCONTROL=ignoreboth
# increase history file size
HISTFILESIZE=1000000
# increase history size
HISTSIZE=${HISTFILESIZE}
# append new entries from memory to .bash_history, and vice-versa
export PROMPT_COMMAND="history -a; history -n; ${PROMPT_COMMAND}"
```

## Usage
​
Making an alias should be the most convenient option, so you can add this to `~/.bash_aliases`:

```sh
alias hh=hstr-rs
```
​
## Screencast

![screenshot](hstr-rs.gif)

