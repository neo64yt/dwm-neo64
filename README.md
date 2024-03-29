# dwm-pyromorphite

dwm-pyromorphite (formerly dwm-neo64) is a heavily customized build of dwm (based on dwm-6.2) and a part of Pyromorphite Desktop. Since I have used this build without any new customization for at least two years, and I'm also slowly switching to Wayland (via [dwl-pyromorphite](https://codeberg.org/neo64yt/dwl-pyromorphite)), do not ever expect it to have frequent updates and new patches applied (or even be rebased on the latest version of upstream dwm). I only keep this as an X fallback of my personal desktop setup.  

## Screenshot

![screenshot](dwm.png)

## Patches used in this build

* actualfullscreen
* alternativetags
* alwayscenter
* aspectresize
* attachaside
* awesomebar (2020-09-07 version)
* bar height
* centeredmaster
* clientindicatorshidevacanttags
* colorbar
* decorhints
* ewmhtags
* fixborders
* gaplessgrid
* monoclesymbol
* nodmenu
* resizecorners
* restartsig
* systray
* swallow
* underlinetags (modified)
* winicon

## Dependencies

* Xlib
* libxcb
* xcb-res
* Imlib2
* libxft
* libxinerama
* JetBrains Mono font
* Material Design Icons font

## Installation guide

### 1. Cloning this repository

Run this command:

```bash
git clone https://codeberg.org/neo64yt/dwm-pyromorphite
```

### 2. Installing dwm

You can either run the installation script (`install.sh`) or run this in the terminal:

```bash
sudo make install 
```

### 3. Running dwm and autostarting applications

#### Autostarting

Autostart applications must be put in `$XDG_CONFIG_HOME/dwm/autostart.sh`. It will automatically be executed by `/usr/local/bin/dwm-session`.

This is a sample of `autostart.sh`:

```bash
#!/bin/sh
# This example script starts mate-polkit and sxhkd with a custom config file
/usr/lib/mate-polkit/polkit-mate-authentication-agent-1 &
sxhkd -c $XDG_CONFIG_HOME/dwm/sxhkdrc &
```

#### Running dwm (with a display manager)

A desktop entry file for dwm will be automatically installed to `/usr/share/xsessions/`.

#### Running dwm (without a display manager)

Put `exec /usr/local/bin/dwm-session` into your `.xinitrc` file.

## Making new customizations

You may want to make customizations on this dwm build to have it as your own. Just like the upstream build of dwm (or any other suckless software), customizations are made by editing the source code (mainly `config.def.h`) and applying patches. For a patching guide, refer to https://dwm.suckless.org/customisation/patches_in_git/ (the recommended method) or if you prefer not to use git, the method to do it (used by many dwm users, including me with this build) is:

```bash
patch -p1 < /path/to/patch.diff
```

When all the customizations you want to make are done, run the `cleandir.sh` script before reinstalling dwm again just like in the installation guide above.

## Keybindings

Will be updated soon in the man page!
