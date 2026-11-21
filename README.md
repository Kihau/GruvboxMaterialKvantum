# GruvboxMaterialKvantum

A **custom** [Kvantum](https://github.com/tsujan/Kvantum) (Qt 5 / Qt 6) widget
theme built to go with the GTK theme **Gruvbox-Material-Dark**
([Materia](https://github.com/nana-4/materia-theme)-based, from
[sainnhe/gruvbox-material](https://github.com/sainnhe/gruvbox-material)).

This is not just a palette swap: buttons, menus, entries, tabs, scrollbars and
indicators are re-shaped to follow the GTK theme's design.

## What it reproduces

| Element | Styling |
|---|---|
| Corners | 6px rounded buttons, menus, combos, tooltips; 6px list selections |
| Surfaces | window/base `#282828`, menus/buttons `#3C3836`, menubar/titlebar `#32302f` |
| Text | `#d4be98`; menubar/titlebar `#ddc7a1`; disabled at 50% |
| Menus | `#3C3836` body, 1px `#d4be98` @ 20% border, 6px corners, cream-8% item hover |
| Buttons | `#3C3836` → hover `#423d3a` → pressed `#48433e` → checked `#443f3c` (+accent text) |
| Entries | cream-4% fill, 6px top corners, 1px cream-30% underline, 2px accent underline on focus |
| Menubar | flat `#32302f`, cream-12% hover |
| Item views | cream-4% hover, `#7c6f64` @ 60% selection (6px rounded) |
| Tabs | flat, 2px `#7c6f64` underline on the active tab |
| Progress | 4px bar, `#7c6f64` fill on a cream-20% trough |
| Scrollbars | pill sliders, cream 50% (60% hover / 70% drag) |
| Checks / radios | the GTK theme's Material symbolic icons |
| Tooltip | cream `#d4be98` with dark text (see note) |

## Known differences from GTK

- **Tooltips are light, not dark.** Qt's `QToolTip` keeps a private palette
  that defaults to black text; Kvantum cannot change it, so a dark tooltip
  would be unreadable. If your apps set `QToolTip::setPalette()`, you can make
  `tooltip-normal` dark again.
- Popup menus have **no drop shadow**. Kvantum only draws the rounded menu
  frame when shadows are disabled (`shadowless_popup=true`).
- GTK's ripple animation has no Kvantum equivalent.
- Widget metrics are close but not pixel-identical, and GTK-specific
  application rules have no Qt counterpart.

## Install

```sh
ln -sfn "$PWD" ~/.config/Kvantum/GruvboxMaterialKvantum
printf '[General]\ntheme=GruvboxMaterialKvantum\n' > ~/.config/Kvantum/kvantum.kvconfig
```

Or symlink it and pick **GruvboxMaterialKvantum** in *Kvantum Manager*.
Restart Qt applications to pick it up.

For the GTK font and icon theme as well:

```sh
# next to QT_STYLE_OVERRIDE=kvantum, e.g. in /etc/environment
QT_QPA_PLATFORMTHEME=gtk3
```

## Branches

- `main` — the earlier plain palette retune of *Gruvbox-Dark-Brown*.
- `custom` — this re-shaped build.

## Credits

- Based on *Gruvbox-Dark-Brown* by sachnr, itself based on **KvAdapta** by
  Pedram Pourang (Tsu Jan).
- Colors and design metrics from **Gruvbox-Material-Dark** (MIT).
- Checkbox/radio icon paths from that theme's symbolic icons.
- Gruvbox color scheme by Pavel Pertsev.

Licensed under the GNU GPL v3 (see `LICENSE`), following the Kvantum themes
this work is derived from.
