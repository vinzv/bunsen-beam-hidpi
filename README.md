## Bunsenlabs Beam-HiDPI
Bunsenlabs "Helium" [theme](https://github.com/BunsenLabs/bunsen-themes/tree/helium-dev/themes/Beam) adapted for HiDPI / 4K / reasonable resolutions.

#### Things included

1. Gtk2
2. Gtk3
3. Openbox
4. xfce4-notify
5. tint2
6. conky

#### Installation

1. Copy the folder ``Beam-HiDPI`` either to your home folder at ``~/.themes/`` or (for system-wide use) to ``/usr/share/themes/``. The latter is recommended if you want to use the theme with LightDM but needs root privileges for installation.
Afterwards select the theme both at:
	* ``Preferences -> Appearance -> Window``
	* ``Preferences -> Openbox -> GUI Config Tool -> Theme``
2. Import file ``tint2rc-hidpi`` via ``Preferences -> Tint2 -> Edit Tint2s -> Tint2 Config GUI`` and activate it there.
3. Copy file ``BL-HiDPI.conkyrc`` to your home folder and place it at ``~/.config/conky/``. The tool at ``Preferences -> Conky -> Conky Chooser`` lets you select it now.

#### Manual tweaks needed
Add these two lines to ``~/.Xresources`` and re-login or run ``xrdb -merge ~/.Xresources`` to activate. For ``Xft.dpi`` uncommenting and adjusting line 7 is fine, too. Just remove the leading '``!``' and replace ``96`` by ``160``.

```
Xft.dpi: 160
Xcursor.size: 48
```

I found these values giving the best results but depending on your screen's resolution ymmv. Adjust them to your preferences.

#### What I've done
##### Gtk2/3 theme
I backported recent HiDPI tweaks from [Greybird](https://github.com/shimmerproject/Greybird/commit/93ce4be9c2a9477daab376c8f76afcc6513d9467) and resized various elements like toolbar buttons, checkboxes and radio buttons.

##### Openbox
I resized and manually redrawed the window buttons.

##### tint2
Set the following values:

* Panel: height 48
* Task Buttons: Max width/height 45, padding 4, spacing 4
* Tray: padding horizontal 8, vertical 4, spacing 6, icon size 
* Clock: font size 16
* Tooltip: padding 4, font size 16

##### conky
Set the following values:

* minimum_width: 400
* maximum_width: 500
* gap_x: 100
* gap_y: 110

#### Done / To do
- [x] Gtk Theme
- [x] Openbox
- [x] tint2 
- [x] conky
- [ ] LightDM Gtk greeter window does not scale
- [ ] PNmixer tray icon does not scale
