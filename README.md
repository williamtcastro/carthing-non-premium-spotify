# Car Thing Non-Premium Spotify

This repo enables the use of the Car thing with a non-premium Spotify account. It removes the need to have the premium account to use the Car Thing but you still have the usual limitations of the Spotify free besides you’re now able to chose the song on the playlist and voice commands works as normal.  

## Tools required

- [ADB Tools](https://www.xda-developers.com/install-adb-windows-macos-linux/)
- [Python3](https://www.python.org/)
- [Pyamlboot](https://github.com/superna9999/pyamlboot)
- [Superbird Tool - by Bishopdynamics](https://github.com/bishopdynamics/superbird-tool)

## Installation

Flash the already jailbroken firmware provided [here](https://github.com/err4o4/spotify-car-thing-reverse-engineering/issues/22#issue-1432896381) from lmore377 into your Car Thing or use **Superbird Tool** to flash the firmware.

Run the commands below:

```bash
# 1 - Enable carthing to write files
adb shell mount -o remount,rw /

# 2 - Setup carthing without need the phone app
adb push settings/onboarding_status /var/lib/qt-superbird-app/settings
adb push settings/setup_state /var/lib/qt-superbird-app/settings

# 3 - Save the original app
adb shell mv /usr/share/qt-superbird-app/webapp /usr/share/qt-superbird-app/webapp-orig
adb push webapp /usr/share/qt-superbird-app/

# 4 - Reboot the device
adb shell reboot
```

Pair with your phone via bluetooth and it’s done.

## Troubleshooting

If you’re car thing us paired with your phone, unpair it and then pair it again after the installation process.

## Warranty and Liability

None. This changes the original firmware from Spotify, and if a OTA Update is made these changes will probably be reverted. By using this tool, you accept responsibility for the outcome.