This is a mirror of: https://www.vim.org/scripts/script.php?script_id=2140

# xoria256
Soft pastel gamma on dark background, same appearance in {,g}vim

A VIM color scheme created by: [Dmitriy Zotikov](https://www.vim.org/account/profile.php?user_id=13852)

Notes:
This colorscheme tries to follow the "traditional" colour semantics found in some IDEs: cold (blue-ish) hues for control structures, warm colors for data, (green would look for comments, but it's difficult to pick an appropriate value for the dark background with only 256 colors available plus a little hard to read, so they are grey). Colors should look almost similar in vim, running in any modern terminal emulator (like recent versions of xterm or konsole), and in GTK2 GUI.

install details
Your terminal should support 256-color terminfo definitions.  For that, install 'ncurses-term' or similar package (not installed in Ubuntu-8.10 by default, btw). Then check that you have $TERM variable properly defined (`echo $TERM` gives something like "xterm-256color"). I use gnome-terminal, and I additionally put the following into ~/.bashrc:

```bash
if [ "$COLORTERM" == "gnome-terminal" ]; then
    export TERM=xterm-256color
fi
```

If you plan to use screen multiplexer, you'll also have to assure, that your ~/.screenrc contains the following stuff:

```bash
term screen-256color
attrcolor b ".I"
# Tell screen how to set colors. AB = background, AF=foreground
termcapinfo xterm 'Co#256:AB=\E[48;5;%dm:AF=\E[38;5;%dm'
# Erase background with current bg color.  Not needed if TERM=screen-256color
defbce "on"
```

When everything is set and done, copy xoria256.vim into ~/.vim/colors.  To use it, issue ':colo xoria256' in {,g}vim.
