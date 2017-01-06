#!/usr/bin/env python


from __future__ import print_function, division

import subprocess
import os
import stat
import math
import time

# Interval (in seconds) to read from light sensor
INTERVAL=5
MAX_ILLUM=500
MIN_ILLUM=22
MAX_BRIGHT=100
MIN_BRIGHT=20
ALP_DEV="/sys/bus/iio/devices/iio:device0/in_illuminance_raw"


def calc_brightness(illum):
    brightness = math.log(illum - (MIN_ILLUM-1)) * 10
    if brightness < MIN_BRIGHT:
        brightness = MIN_BRIGHT
    elif brightness > MAX_BRIGHT:
        brightness = MAX_BRIGHT
    return brightness


if __name__ == '__main__':
    prev_illum = 0
    while True:
        f = open(ALP_DEV, 'r')
        illum = int(f.read())
        f.close()
        if illum  == prev_illum:
            continue
        print("illum: " + str(illum))
        brightness = round(calc_brightness(illum))
        subprocess.run("/usr/bin/light -S " + str(brightness), shell=True)
        time.sleep(INTERVAL)
