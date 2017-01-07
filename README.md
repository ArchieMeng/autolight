# autolight
Automatically adjust display backlight brightness based on ambient light. autolight requires a device with an ambient light sensor to determine the amount of ambient light and adjust the display backlight brightness accordingly. If your device does not have an ambient light sensor, then this application will not work as you might expect!

### Usage
autolight is designed to be run as a regular user, NOT as root. This application uses the [light](https://github.com/haikarainen/light) application to handle configuring the display backlight.

Modify the included config file and place it in one of these locations (in order of precedence):

```
/etc/autolight/config

~/.config/autolight/config

./config
```


### Installation

#### Arch Linux

Install [autolight package](https://aur.archlinux.org/packages/autolight/) from AUR.

#### Other Linux Folks

autolight looks for a config file (named "config") in ```/etc/autolight/```, ```~/.config/autolight```, and ```./``` (cwd), and will return if no config is found. 

##### Requirements

- A device with an ambient light sensor (e.g. acpi_als). This was tested on a Dell XPS 13 9333 with kernel 4.8.

- [light](https://github.com/haikarainen/light)

- Python 3

- python-configargparse
