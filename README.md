# Hide Cursor Drops: quick setup

This is a copy of [wvmj-dev/hide-cursor-animated](https://github.com/wvmj-dev/hide-cursor-animated),
a GNOME Shell extension that hides the mouse cursor with an animation.
All credit goes to its author, **wvmj-dev**. The original README is kept in
[README_original.md](README_original.md).

Requires GNOME Shell 48–51 on Wayland, plus `git`, `make` and
`glib-compile-schemas` (package `glib2` or `libglib2.0-bin`). Translations
are skipped, so `gettext` is not needed.

## 1. Clone

```sh
git clone https://github.com/wvmj-dev/hide-cursor-animated.git
cd hide-cursor-animated
```

That URL is the upstream repository. To use this copy instead, put this
repository's URL in its place.

## 2. Install

```sh
make install LINGUAS=
```

`LINGUAS=` skips building the translations. The extension is installed to
`~/.local/share/gnome-shell/extensions/hide-cursor-drops@wvmj-dev.github.io/`.

## 3. Load it without logging out

Press **Alt+F2**, type `lg` and press Enter to open Looking Glass. Paste this
into its prompt and press Enter:

```js
Main.extensionManager.loadExtension(Main.extensionManager.createExtensionObject('hide-cursor-drops@wvmj-dev.github.io', Gio.File.new_for_path(GLib.get_home_dir() + '/.local/share/gnome-shell/extensions/hide-cursor-drops@wvmj-dev.github.io'), 2))
```

Close Looking Glass with **Esc**. If you'd rather not use it, logging out and
back in does the same thing.

## 4. Enable

```sh
gnome-extensions enable hide-cursor-drops@wvmj-dev.github.io
```

Open the settings with `gnome-extensions prefs hide-cursor-drops@wvmj-dev.github.io`.

## Update or remove

```sh
git pull && make reload LINGUAS=   # reinstall and restart the extension
make uninstall                     # remove it
```

## License

GPL-2.0-or-later, same as upstream. See [LICENSE](LICENSE).
