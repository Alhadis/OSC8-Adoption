OSC 8 adoption in terminal emulators
====================================
This document tracks in-the-wild support for terminal hyperlinks (a.k.a., [OSC 8](https://gist.github.com/egmontkob/eb114294efbcd5adb1944c9f3cb5feda)), primarily amongst [terminal emulators](https://en.wikipedia.org/wiki/List_of_terminal_emulators).


Testing support
---------------
To determine if your terminal emulator supports hyperlinks, run the following command:

```sh
printf '\033]8;;http://example.com\033\\This is a link\033]8;;\033\\\n'
```

In an OSC 8-compatible terminal, you should see something to the effect of:

> <samp><a href="http://example.com">This is a link</a></samp>


Support
-------
### Terminal emulators
- [Alacritty](https://github.com/alacritty/alacritty/) since [v0.11](https://github.com/alacritty/alacritty/releases/tag/v0.11.0) (2022-10-13)
- [DomTerm](https://domterm.org/) since [1.0.2](https://github.com/PerBothner/DomTerm/commit/19771fa894634d2423d6d097c8203892254dbcf4) (2018-05-09)
- [`foot`](https://codeberg.org/dnkl/foot/): Since [1.7.0](https://codeberg.org/dnkl/foot/releases/tag/1.7.0) (2021-03-20)
- [hterm](https://chromium.googlesource.com/apps/libapps/+/HEAD/hterm/) since [1.76](https://github.com/chromium/hterm/releases/tag/v1.76) (2018-06-21)
- [Hyper](https://hyper.is/) since Oct 2019
- [iTerm2](http://iterm2.com/) 3.1
- [Kitty](https://github.com/kovidgoyal/kitty/issues/68) since v0.19: [issue](https://github.com/kovidgoyal/kitty/issues/68)
- [Konsole](https://konsole.kde.org/) since [Jul 2020](https://invent.kde.org/utilities/konsole/-/merge_requests/138)
- [mintty](http://mintty.github.io/) since [2.9.7](https://github.com/mintty/mintty/releases/tag/2.9.7) (2019-03-15)
- [Terminology](https://www.enlightenment.org/about-terminology) in Git since 2018-10-14, probably will be released in version 1.3
- [Ultimate++ terminal widget](https://github.com/ismail-yilmaz/upp-components/tree/master/CtrlLib/Terminal) since Nov 2019
- [VTE-based](https://wiki.gnome.org/Apps/Terminal/VTE): since 0.50[^1]
  - [GNOME Terminal](https://wiki.gnome.org/Apps/Terminal) 3.26
  - [Guake](http://guake-project.org/) 3.2.1
  - [ROXTerm](https://github.com/realh/roxterm) 3.5.1
  - [Terminator](https://github.com/gnome-terminator/terminator)[^2]: since [v2.0](https://github.com/gnome-terminator/terminator/blob/v2.0/CHANGELOG.md) (2020-10-07)
  - [Tilix](https://github.com/gnunn1/tilix) 1.5.8
  - [xfce4-terminal](https://docs.xfce.org/apps/xfce4-terminal/start) Staged for v1.2 release on [2022-11-07](https://gitlab.xfce.org/apps/xfce4-terminal/-/commit/56334dbcda7bd54fca681d3de6cb63014dbf08b0)
- [WezTerm](http://wezfurlong.org/wezterm/index.html) since early 2018
- [Windows Terminal](https://github.com/microsoft/terminal/issues/204) since [v1.4.3141.0](https://github.com/microsoft/terminal/releases/tag/v1.4.3141.0) (2020-11-12)
- [xterm.js](https://xtermjs.org/) since [5.0.0](https://github.com/xtermjs/xterm.js/releases/tag/5.0.0) (2022-09-16)

### Terminal multiplexers
- [TermySequence](https://termysequence.io/)
- [`tmux`](https://github.com/tmux/tmux): Staged for release on [2022-06-30](https://github.com/tmux/tmux/commit/cdacc12ce305ad2f3e65e2a01328a988e3200b51)[^3]
  - [`tmux-hyperlink`](https://github.com/ppwwyyxx/tmux-hyperlink): Fork of `tmux` with out-of-the-box support

### Apps
- [Neovim](https://neovim.io/): latest version supports rendering texts with hyperlinks (since [this PR](https://github.com/neovim/neovim/pull/27109)).
- [Emacs](https://www.gnu.org/software/emacs/): Since [28.1](https://www.gnu.org/software/emacs/news/NEWS.28.1) (2022-04-04)
- [`eza`](https://eza.rocks/): (successor to [`exa`](https://github.com/ogham/exa/issues/396#issuecomment-1834264733)): Since version [v0.10.3](https://github.com/eza-community/eza/releases/tag/v0.10.3) (2023-07-31)
- [GCC](https://gcc.gnu.org/): Since version 10 (and [greatly expanded in version 14](https://gcc.gnu.org/pipermail/gcc-patches/2023-November/635186.html)), for [diagnostic messages to point to the documentation](https://gcc.gnu.org/onlinedocs/gcc-10.1.0/gcc/Diagnostic-Message-Formatting-Options.html#index-fdiagnostics-urls).
- [Delta](https://github.com/dandavison/delta): Since [v0.4](https://github.com/dandavison/delta/releases/tag/0.4.0) (2020-08-04), for linking to files and GitHub commits
- [groff](https://www.gnu.org/software/groff/): Since [1.23.0](https://git.savannah.gnu.org/cgit/groff.git/tag/?h=1.23.0) (2023-07-05), for links in `roff` documents, including man pages.
- [`less -R`](http://greenwoodsoftware.com/less/): since [v566](https://github.com/gwsw/less/commit/0f810ef16781bf0f59690be63af876bddabf68bf) (2020-11-25)
- [`ls --hyperlink[=always/auto/never]`](https://www.gnu.org/software/coreutils/manual/html_node/ls-invocation.html#ls-invocation): since [`coreutils` v8.28](https://github.com/coreutils/coreutils/blob/v8.28/NEWS#L88-L89) (2017-09-02).
- [`lsd --hyperlink[=always/auto/never]`](https://github.com/Peltoche/lsd/): since lsd 0.22 (2022-04).
- [Matterhorn](https://github.com/matterhorn-chat/matterhorn) chat client: Since version 40400.0.0.
- [mdcat](https://github.com/lunaryorn/mdcat) (markdown cat): Since version 0.5.0.
- [moar](https://github.com/walles/moar) (pager, `less` replacement): Since version [v1.14.0](https://github.com/walles/moar/releases/tag/v1.14.0) (2023-05-03)
- [Symfony](https://symfony.com/): Since version 4.3.
- [systemd](https://github.com/systemd/systemd): Since version 239.
- [wget2](https://gitlab.com/gnuwget/wget2/): Since Nov 2019


### Libraries
- [`ansi_up`](https://github.com/drudru/ansi_up/) ANSI code-to-HTML conversion library: Since [v4.0.3](https://github.com/drudru/ansi_up/releases/tag/v4.0.3) (2019-02-12)
- [`brick`](https://hackage.haskell.org/package/brick) high-level terminal UI library: Since October 2017.
- [Rich](https://github.com/willmcgugan/rich) rich-text formatting library: Since May 2020.
- [`vty`](https://hackage.haskell.org/package/vty) medium-level terminal UI library: Since October 2017.


Pending feature requests
------------------------
### Terminal emulators
- [ConEmu](https://github.com/Maximus5/ConEmu/issues/2078)
- `VTE`-based:
  - [LilyTerm](https://github.com/Tetralet/LilyTerm/issues/117)
  - [LXDE Terminal](https://sourceforge.net/p/lxde/bugs/870/)
  - [MATE Terminal](https://github.com/mate-desktop/mate-terminal/issues/175)
  - [Tilda](https://github.com/lanoxx/tilda/issues/285)

### Terminal multiplexers
- [`screen`](https://savannah.gnu.org/bugs/index.php?50952)

### Apps
- [Irssi](https://github.com/irssi/irssi/issues/700)
- [TBVaccine](https://github.com/skorokithakis/tbvaccine/issues/37)
- [WeeChat](https://github.com/weechat/weechat/issues/1252)


Links
-----
- [Original OSC 8 specification](https://gist.github.com/egmontkob/eb114294efbcd5adb1944c9f3cb5feda)
- [GNOME Terminal discussion](https://bugzilla.gnome.org/show_bug.cgi?id=779734)
- [iTerm2 discussion](https://gitlab.com/gnachman/iterm2/issues/5158)
- [Test file](https://git.gnome.org/browse/vte/plain/perf/hyperlink-demo.txt)


<!-- Footnotes -->
[^1]: Use VTE 0.50.4, 0.52.2, or newer to avoid a rare crash.
[^2]: Refers to the "Terminator" program written in Python for Linux, based on GTK+. Not to be confused with the one written in Java [bearing the same name](https://code.google.com/archive/p/jessies/wikis/Terminator.wiki).
[^3]: Requires user to add `set -ga terminal-features "*:hyperlinks"` to their tmux config
