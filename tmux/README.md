# My tmux config

This is the tmux configuration I use daily for development, servers, and long-running sessions.
It focuses on fast navigation, sane defaults, and muscle-memory-friendly keybindings.
No plugins, no frameworks, just tmux behaving properly.

---

## installation

Put the config in your home directory as `.tmux.conf`:

```bash
cp tmux.conf ~/.tmux.conf
```

Reload tmux without restarting sessions:

```bash
tmux source-file ~/.tmux.conf
```

Or from inside tmux:

```
Ctrl-a r
```

---

## prefix key

The default tmux prefix (`Ctrl-b`) is replaced with:

```
Ctrl-a
```

All tmux commands start with this prefix.

To send a literal `Ctrl-a` to a program, press it twice.

---

## panes

**splitting**

```
Ctrl-a \     split horizontally (left/right)
Ctrl-a -     split vertically (top/bottom)
```

**navigation**

```
Ctrl-a h     move left
Ctrl-a j     move down
Ctrl-a k     move up
Ctrl-a l     move right
```

**resizing (repeatable)**

```
Ctrl-a H     resize left
Ctrl-a J     resize down
Ctrl-a K     resize up
Ctrl-a L     resize right
```

Vim-style keys everywhere. No arrow keys required.

---

## windows

Windows behave like predictable tabs.

```
Ctrl-a c         create window
Alt + Left       previous window
Alt + Right      next window
Ctrl-a x         kill current pane
```

Windows are numbered starting from 1, and tmux automatically renumbers them when one is closed.

Automatic window renaming is disabled.

---

## copy mode (vim-like)

tmux copy mode is configured to use Vim keys.

```
Ctrl-a [     enter copy mode
v            start selection
y            copy and exit
Ctrl-a p     paste
```

Works over SSH and does not depend on the system clipboard.

---

## mouse

Mouse support is enabled:

* Resize panes
* Scroll tmux history
* Select panes and windows

Keyboard usage remains first-class.

---

## status bar

The status bar shows:

* Session name
* Window list
* Date and time

It updates periodically and highlights activity without being noisy.
Designed to be readable, not decorative.

---

## terminal and colors

True color and 256-color support are explicitly enabled.

This avoids broken themes in:

* Vim / Neovim
* less
* modern shells

Terminal is advertised as `tmux-256color`.

---

## notes

This config intentionally avoids plugins and heavy customization.
tmux rewards simplicity and punishes cleverness.

If you extend it, do so slowly and with intent.

