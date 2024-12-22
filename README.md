# Monitor Modet

This script allows you to control various settings of a monitor connected via DDC/CI, including brightness, contrast, volume, and color adjustments (red, green, blue). It also lets you switch between different display modes. The script uses the `ddcutil` command to interact with the monitor.

## Features
- **Brightness Control**: Get or change the brightness of the monitor.
- **Contrast Control**: Get or change the contrast of the monitor.
- **Volume Control**: Get or change the volume level of the monitor.
- **Color Adjustment**: Adjust red, green, and blue color channels.
- **Display Mode Switching**: Switch between predefined monitor modes (e.g., Gamer 1, FPS Mode, etc.).

## Requirements
- `ddcutil`: This utility is required to communicate with the monitor over DDC/CI.
- `i2c-dev` module for I2C communication.

## Installation
1. Ensure `ddcutil` is installed. You can install it via your package manager or from source.
   - For Ubuntu: `sudo apt install ddcutil`
   - For other systems, refer to the [ddcutil documentation](https://github.com/rockowitz/ddcutil).

2. Ensure the `i2c-dev` module is loaded by running:
   ```bash
   sudo modprobe i2c-dev

### Usage

./monitor_control.sh [OPTIONS]

Available Options:

`-l <value_of_brightness>`

Set the brightness (value between 0 and 100).

Example:

`./monitor_control.sh -l 50`

This sets the brightness to 50.

------------


`-c <value_of_contrast>`

Set the contrast (value between 0 and 100).

Example:

./monitor_control.sh -c 70

This sets the contrast to 70.

------------


`-m <mode_of_the_monitor>`

Set the display mode. Accepts:

    0 for Default Mode
    1 for Gamer 1 Mode
    2 for Gamer 2 Mode
    3 for Game 3 Mode
    fps for FPS Mode
    racing for Racing Mode
    rts for RTS Mode
    Or a custom hex value (e.g., 0x0e for Gamer 1 Mode).

Example:

`./monitor_control.sh -m 1`

This changes to Gamer 1 mode.

------------


`-v <value_of_volume>`

Set the volume (value between 0 and 100).

Example:

`./monitor_control.sh -v 60`

This sets the volume to 60.

------------


`-r <value_of_red>`

Set the red color channel (value between 0 and 100).

Example:

`./monitor_control.sh -r 80`

This sets the red channel to 80.

------------


`-g <value_of_green>`

Set the green color channel (value between 0 and 100).

Example:

`./monitor_control.sh -g 70`

This sets the green channel to 70.

------------


`-b <value_of_blue>`

Set the blue color channel (value between 0 and 100).

Example:

`./monitor_control.sh -b 60`

This sets the blue channel to 60.


------------


### Get Current Values:

For any of the options `(-l, -c, -v, -r, -g, -b)`, use `g` as the argument to get the current value.

Example:

`./monitor_control.sh -l g`

This will display the current brightness value.

------------


### Mute/Unmute Volume:

To mute or unmute the volume, pass `m` as the argument to `-v.`

Example:

`./monitor_control.sh -v m`

This toggles mute/unmute.

------------

