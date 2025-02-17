### Ubuntu Mainline Kernel Installer
A tool for installing the latest Linux kernels on Ubuntu-based distributions.

![Main window screenshot](main_window.png)

### Features
* Fetches the list of available kernels from the [Ubuntu Mainline PPA](http://kernel.ubuntu.com/~kernel-ppa/mainline/)
* Optionally watches and displays notifications when a new kernel update is available
* Downloads and installs packages automatically
* Display available and installed kernels conveniently
* Install/Uninstall kernels from gui
* For each kernel, the related packages (headers & modules) are installed or uninstalled at the same time

### Install
Minimal .deb packages are in [releases](../../releases/latest). (Usually just a single deb for any given release).

Better: [cappelikan](https://github.com/cappelikan) maintains a [PPA](https://code.launchpad.net/~cappelikan/+archive/ubuntu/ppa)
```
sudo add-apt-repository ppa:cappelikan/ppa
sudo apt update
sudo apt install mainline
```

### Build
```
sudo apt install libgee-0.8-dev libjson-glib-dev libvte-2.91-dev valac aria2 lsb-release aptitude make gettext dpkg-dev
git clone https://github.com/bkw777/mainline.git
cd mainline
make
sudo make install
```

### Usage
Look for System -> Ubuntu Mainline Kernel Installer in your desktop's Applications/Start menu.

Otherwise:  
CLI
```
mainline --help
mainline
```
GUI
```
mainline-gtk
```
### Help
* Secure Boot -> Possibly useful, I have not tried: https://github.com/M-P-P-C/Signing-a-Linux-Kernel-for-Secure-Boot

* Kernel versions 5.15.7+ and libssl3 -> [Install libssl3](../../wiki/Install-libssl3)

### About
mainline is a fork of [ukuu](https://github.com/teejee2008/ukuu)  
The original author stopped maintaining the original GPL version of ukuu and switched to a [paid license](https://teejeetech.in/tag/ukuu/) for future versions.

### Enhancements / Deviations from the original author's final GPL version
* Changed name from "ukuu" to "mainline"
* Removed all GRUB options
* Removed all donate buttons, links, dialogs
* Remove source cruft
* Better temp and cache directory behavior
* Better desktop notification behavior

### TODO & WIP
* Make the notification bg process detect when the user logs off and exit itself.
* Move the notification/dbus code into the app and make an "applet mode"
