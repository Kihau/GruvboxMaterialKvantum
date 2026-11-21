# GruvboxMaterialKvantum

A [Kvantum](https://github.com/tsujan/Kvantum) (Qt 5 / Qt 6) widget theme whose
palette matches the GTK theme **Gruvbox-Material-Dark**.

It is a retune of the Kvantum theme *Gruvbox-Dark-Brown* by sachnr (itself
based on KvAdapta), with the colors and surfaces taken from the GTK theme's
`gtk-3.0/gtk.css`:

| Surface | Color |
|---|---|
| window / base | `#282828` |
| menu background | `#3C3836` |
| menu border | `#d4be98` @ 20% |
| text | `#d4be98` |
| secondary / disabled text | `#928374` / `#d4be98` @ 50% |
| highlight / selection | `#7c6f64` @ 60% |
| hover tint (menus, buttons, rows) | `#d4be98` @ 8% |
| button | `#3C3836` (hover `#423d3a`, pressed `#48433e`, checked `#443f3c`) |
| menubar / titlebar | `#32302f` / text `#ddc7a1` |
| tooltip | `#32302f` @ 90% |
| links | `#7daea3` |

## Install

Kvantum looks for themes in `~/.config/Kvantum`, so link this repository there
and select the theme:

```sh
ln -sfn "$PWD" ~/.config/Kvantum/GruvboxMaterialKvantum
printf '[General]\ntheme=GruvboxMaterialKvantum\n' > ~/.config/Kvantum/kvantum.kvconfig
```

Alternatively, symlink it and pick **GruvboxMaterialKvantum** in *Kvantum Manager*.

Qt applications pick the theme up when they are restarted. To refresh already
open apps without a restart, switch to another theme and back in Kvantum
Manager.

## Fonts and icons

Kvantum only styles widgets; it does not set the font or icon theme. To also
inherit the GTK font and the `Gruvbox-Material-Dark` icon theme, use the GTK
platform theme together with Kvantum:

```sh
# e.g. in /etc/environment, next to QT_STYLE_OVERRIDE=kvantum
QT_QPA_PLATFORMTHEME=gtk3
```

Kvantum still wins for the widget style/palette; the platform theme only adds
fonts, icons, and native file dialogs.

## Notes

This is an approximate visual match, not a port. Things that differ from GTK:

- corners are square instead of 6px rounded (the geometry was left untouched);
- GTK's ripple animation has no Kvantum equivalent;
- GTK-specific per-application rules have no Qt counterpart.

## Credits

- *Gruvbox-Dark-Brown* by sachnr, based on KvAdapta by Pedram Pourang (Tsu Jan).
- Palette from **Gruvbox-Material-Dark** (Gruvbox GTK theme by Fausto-Korpsvart).
- Gruvbox color scheme by Pavel Pertsev.
