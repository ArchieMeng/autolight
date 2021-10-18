# smartlight

smartlight was developed from Clayton Craft (craftyguy)'s autolight repo and original repo is on [here](https://gitlab.com/craftyguy/autolight)

This repo is my modified version of autolight.

Automatically adjust display backlight brightness based on ambient light. smartlight requires a device with an ambient light sensor to determine the amount of ambient light and adjust the display backlight brightness accordingly. If your device does not have an ambient light sensor, then this application will not work as you might expect!

Smooth transitioning between brightnesses is also supported, though in a rather hackish form at the moment.

### Usage
smartlight is designed to be run as a regular user, NOT as root. This application uses the [light](https://github.com/haikarainen/light) application to handle configuring the display backlight. (SOMETIMES LIGHT MAY NOT BE ABLE TO CONTROL SCREEN BRIGHTNESS AT FIRST AS LONG AS THE CURRENT USER IS NOT IN VIDEO GROUP)

Modify the included config file and place it in one of these locations (in order of precedence):

```
./config

~/.config/smartlight/config


/etc/smartlight/config

```
See the sample ```config``` file for available configuration options. At the very least, you'll need to set the ALS device.

### Installation

#### Arch Linux

Install [smartlight package](https://aur.archlinux.org/packages/smartlight/) from AUR.

#### Other Linux Folks

smartlight looks for a config file (named "config") in ```/etc/smartlight/```, ```~/.config/smartlight```, and ```./``` (cwd), and will return if no config is found.

##### Requirements

- A device with an Ambient Light Sensor (e.g. acpi_als). This was tested on a Dell XPS 13 9333 with kernel 4.8.

- [light](https://github.com/haikarainen/light)

- Python 3

- python-configargparse
