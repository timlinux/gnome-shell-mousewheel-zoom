# gnome-shell-mousewheel-zoom

(c) Sep 2011, Tobias Quinn <tobias@tobiasquinn.com>

GPLv3

This uses python-xlib and python-dbus to allow the gnome shell to be zoomed
like enhanced zoom desktop in compiz using the modification key and mouse scrollwheel

## Configuration
To select the modifier key use dconf-editor and navigate to:
com -> tobiasquinn.com -> mousewheelzoom -> modifier-key
Note: mousewheelzoom needs to be restarted to reload the configuration

Note: config only works with the precise and quantal builds (master branch)

## Branches
The branches have recently changed master is for gnome 3.4 onwards (ubuntu precies and quantal).

oneiric branch is for ubuntu oneiric and uses python-xlib

There is also a ubuntu precise port using gsettings in the branch precise-gsettings.

## Arch Linux
There is an archlinux PKGBUILD provided (available from AUR as gnome-shell-mousewheel-zoom-git)

## Linux Mint 15
For Linux Mint 15 olivia (Ubuntu 13.04 raring) this is the installation procedure that worked for me:

```bash
sudo apt-get install git valac libx11-dev
mkdir ~/src ; cd ~/src
git clone https://github.com/tobiasquinn/gnome-shell-mousewheel-zoom.git
cd gnome-shell-mousewheel-zoom ; make
sudo cp com.tobiasquinn.mousewheelzoom.gschema.xml /usr/share/glib-2.0/schemas/
sudo glib-compile-schemas /usr/share/glib-2.0/schemas
./mousewheelzoom (<-- add to mdm startup applications)
```

## Ubuntu
A ppa for Ubuntu oneiric, precise and quantal is available from:

https://launchpad.net/~tobias-quinn/+archive/gsmz

to install do:

```bash
sudo add-apt-repository ppa:tobias-quinn/gsmz
sudo apt-get update
sudo apt-get install gnome-shell-mousewheel-zoom
```

## Fedora
To be able to compile (using `make`) the vala version, run:

```bash
yum -y install vala gobject-introspection-devel libX11-devel
```

## hideonzoom.py
There's also hideonzoom.py which hides the cursor during inactivity. It needs unclutter package.

## Troubleshooting
1) Check `ps aux | grep 'mousewheelzoom'` and possibly kill any other instance.

