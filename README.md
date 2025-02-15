
# maimai-windows-touch-panel

A script to record touch events on Windows devices and simulate maimai partition touch screens.

The software simulates partition touch, which can be used on custom maimai handheld devices.

## Usage

1. First, change the value of `DummyTouchPanel` in the game configuration file to `0`.
2. Windows Settings - Bluetooth and other devices - Touch - Three-finger and four-finger touch gestures - Turn off.
3. Accessibility - Mouse pointer and touch - Touch indicator - Turn off.
4. Control Panel - Hardware and Sound - Pen and Touch - Turn off "Show visual feedback when touching the screen" in "Touch feedback".
5. Control Panel - Hardware and Sound - Pen and Touch - Turn off "Use touch to right-click" in "Touch actions".
6. Open any image editing tool, prepare an image the same size as the display screen (e.g., 2160x3840), place `./image/color_exp_panel.png` in the circular touch area of the image, and save the edited image in the script's `image` directory as `image_monitor.png`.
7. Edit the `config.yaml` configuration file, modify the `exp_image_dict` configuration, and change the RGB channel color values of each block to the corresponding block color values of the edited image (usually, the default values are fine).
8. If there is no Python environment on your computer, please download and install it from the [official website](https://www.python.org/).
9. Double-click `install.bat` to install dependencies.
10. Edit the `config.yaml` configuration file and modify multiple configurations according to the instructions in the file.
11. Download a `VSPD` virtual serial port tool and establish forwarding between `COM3` and `COM33`.
12. Connect the touch screen to the computer, double-click `start.bat` (if there are two screens, execute it on the screen where the game will run). The script will generate a transparent window at the front of the screen to capture touch actions (use `Win+Tab` to select other windows), then run the game (the game must be run in windowed mode). The script console will output `Connected to the game` when ready.
13. Adjust the delay of judgment A/B in the game until it is usable. The transparent window must always be the topmost window while playing.
14. Play a game to see if the touch is responsive and adjust the `AREA_SCOPE` variable based on the experience.
15. If the single-point delay is low but the delay increases during sliding, set `TOUCH_THREAD_SLEEP_MODE` in the script to false, or reduce the value of `TOUCH_THREAD_SLEEP_DELAY` (if it still lags, please submit an issue for feedback).

## Command List

If the connection is accidentally disconnected during the game, type `start` in the console and press Enter to reconnect to the game.

Type `reverse` to adjust the screen orientation of the touch device.

Type `restart` to reload the configuration file/restart the script.

## Note

To add 2P, simply copy the script and add forwarding from COM4 to COM44.

This script is for testing purposes only.

## Similar Projects

[maimai-android-touch-panel](https://github.com/ERR0RPR0MPT/maimai-android-touch-panel)

## License

[MIT License](https://github.com/ERR0RPR0MPT/maimai-windows-touch-panel?tab=MIT-1-ov-file)

## Others

The edited block image looks like this:

![](https://raw.githubusercontent.com/ERR0RPR0MPT/maimai-android-touch-panel/main/image/image_monitor.png)
