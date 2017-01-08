# autolight
Automatically adjust display backlight brightness based on ambient light. autolight requires a device with an ambient light sensor to determine the amount of ambient light and adjust the display backlight brightness accordingly. If your device does not have an ambient light sensor, then this application will not work as you might expect!

Smooth transitioning between brightnesses is also supported, though in a rather hackish form at the moment.

### Usage
autolight is designed to be run as a regular user, NOT as root. This application uses the [light](https://github.com/haikarainen/light) application to handle configuring the display backlight.

Modify the included config file and place it in one of these locations (in order of precedence):

```
./config

~/.config/autolight/config


/etc/autolight/config

```
See the sample ```config``` file for available configuration options. At the very least, you'll need to set the ALS device.

### Installation

#### Arch Linux

Install [autolight package](https://aur.archlinux.org/packages/autolight/) from AUR.

#### Other Linux Folks

autolight looks for a config file (named "config") in ```/etc/autolight/```, ```~/.config/autolight```, and ```./``` (cwd), and will return if no config is found.

##### Requirements

- A device with an Ambient Light Sensor (e.g. acpi_als). This was tested on a Dell XPS 13 9333 with kernel 4.8.

- [light](https://github.com/haikarainen/light)

- Python 3

- python-configargparse
