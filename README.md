Not your favorite `skhd` config, but a solid No.2
=================================================

## DESCRIPTION

  Opinionated `skhd` config, but also a few useful AppleScripts.

  - You'll find a number of bindings to front or open specific apps
    by using a global binding.

  - E.g., &lt;`Shift-Ctrl-Cmd-A`&gt; brings forward the browser
    window with an active email tab.

    Or try &lt;`Cmd-Y`&gt; to open a new browser window.

    Bring Slack to the front or open it with &lt;`Shift-Ctrl-Cmd-f`&gt;.

    And more.

  - This project is not really designed to be used directly,
    except by the author:

    - It's intended instead for other devs to reference, copy, or to fork.

  - Specifically, many of the keybindings are more Linux-y.

    - The author uses
      [Karabiner-Elements](https://karabiner-elements.pqrs.org/)
      and a number of modifications (published as
      [Karabiner-Elephants](https://github.com/DepoXy/Karabiner-Elephants))
      to swap most default `Ctrl-` and `Cmd-` key combos, so that
      their macOS behaves more like Linux Mint MATE (the author's
      other main development environment).

## USAGE

  Make a symlink under `~/.config` to this project's config,
  and it'll be wired (see instructions below).

  You can also add your own `skhdrc--client` file to add
  your own bindings (or just fork this repo and make it
  your own, or copy-paste what you need for yourself).

  But first, be aware this project uses absolute paths:

  - Because `skhd` runs on its own, it won't have access to your
    local shell environment, and because this project doesn't
    "install" itself anywhere, it just assumes a particular
    path to the AppleScript files:

        ~/.kit/mOS/macOS-skhibidirc/lib

  - Feel free to fork this repo and change the path prefix to match
    your own environment, otherwise you'll want to clone this project
    at the appropriate path:

        mkdir -p ~/.kit/mOS
        cd ~/.kit/mOS
        git clone https://github.com/DepoXy/macOS-skhibidirc.git

  - (FYI, the `~/.kit` directory is a [DepoXy](https://github.com/DepoXy/depoxy)
    convention, which is the primary user of this project.)

  Once cloned, you can wire this app very simply by symlinking
  the config file, [`.config/skhd/skhdrc`](.config/skhd/skhdrc),
  from `~/.config/skhd/skhdrc`:

      mkdir -p ~/.config/skhd
      ln -sn ~/.kit/mOS/macOS-skhibidirc/.config/skhd/skhdrc \
        ~/.config/skhd/skhdrc

## COMMANDS

### Generic commands

  `<Cmd-f>`: Bring any Finder window to front, or open Finder

  `<Shift-Ctrl-Cmd-W>`: Hide all windows

### Terminal window foregrounders

  `<Cmd-1>`: Bring to front any window whose title starts with "1. "

  `<Cmd-2>`: Bring to front any window whose title starts with "2. "

    ...

  `<Cmd-9>`: Bring to front any window whose title starts with "9. "

  The [Homefries](https://github.com/landonb/home-fries) project
  includes a `PS1` setup that numbers new terminal windows for
  Alacritty, mate-terminal, and iTerm2, specifically:

  https://github.com/landonb/home-fries/blob/release/lib/term/show-command-name-in-window-title.sh

### Browser foregrounders

  `<Shift-Ctrl-Cmd-A>`: Bring the Email or Calendar browser window to
  the front, or open Gmail

  `<Shift-Ctrl-Cmd-S>`: Bring the Messaging browser window to
  the front, or open Messenger

  `<Cmd-P>`: Bring the Power Thesaurus browser window to the front,
  or open it

  `<Shift-Cmd-X>`: Bring the Regex Dictionary by Lou Hevly browser window
  to the front, or open it

### Application foregrounder-openers

  `<Shift-Ctrl-Cmd-F>`: Bring Slack to the front, or open it

  `<Shift-Ctrl-Cmd-X>`: Bring Spotify to the front, or open it

  `<Cmd-Y>`: Open a new Chrome window

  `<Shift-Cmd-Y>`: Bring Chrome to the front

  `<Cmd-R>`: Bring the browser DevTools window to the front

  `<Cmd-M>`: Open a new Alacritty window

  `<Shift-Cmd-M>`: Bring Alacritty to the front

  `<Ctrl-Cmd-M>`: Open a new Terminal.app window

  `<Cmd-Grave>`: Bring MacVim to the front

### Time and date clipboard fillers

  `<Cmd-Minus>`: Put YYYY-MM-DD into clipboard, e.g., "2024-07-08"

  `<Ctrl-Cmd-Semicolon>`: Put dashed date and normal time into clipboard,
  e.g., "2024-07-08 17:14"

  `<Ctrl-Cmd-Apostrophe(Quote)>`: Put dashed date-plus-time into clipboard,
  e.g., "2024-07-08-17-14"

### Private config

  The config finishes by loading an optional "private" config
  that you can symlink alongside the main config:

      ln -sn /path/to/my/private/skhdrc \
        ~/.config/skhd/skhdrc--client

## DEPENDENCIES

  As mentioned above, the `<Cmd-1>` through `<Cmd-9>` bindings expect
  terminal window titles to be numbered.

  - See [Homefries](https://github.com/landonb/home-fries) for a
    `PS1` prompt that titles window, specifically:

    https://github.com/landonb/home-fries/blob/release/lib/term/set-shell-prompt-and-window-title.sh
    https://github.com/landonb/home-fries/blob/release/lib/term/show-command-name-in-window-title.sh

  The Browser foregrounders call `sensible-open` from another project:

  - https://github.com/landonb/sh-sensible-open

  - But you could edit that AppleScript file,
    [lib/raise--chrome--window-or-open.osa](lib/raise--chrome--window-or-open.osa),
    and replace the last command with:

        open location (item 1 of argv)

## SEE ALSO

  This project complements a collection of Karabiner-Elements
  modifications that add bindings beyond the reach of `skhd`

  https://github.com/DepoXy/Karabiner-Elephants#🐘

  This project is one part of a larger dev stack bound together
  by the DepoXy Development Environment Orchestrator

  https://github.com/DepoXy/depoxy#🍯

## AUTHOR

Copyright (c) 2024 Landon Bouma &lt;depoxy@tallybark.com&gt;

This software is released under the MIT license (see `LICENSE` file for more)

## REPORTING BUGS

&lt;https://github.com/DepoXy/macOS-skhibidirc/issues&gt;

