# Activating Thunderbolt station to allow usb to work
This is based on the following thread (https://forum.manjaro.org/t/support-plug-and-play-for-thunderbolt-docking-station/112171).
The dock station is not authorized and it needs to be authorized to activate usb devices. To do this:
1. install `bolt` from the add/remove software
2. in the terminal, run `boltctl` and copy the device uuid (note that an orange dot will appear next to the device name to show that the device is not authorized)
3. run `boltctl enroll your_uuid` to authorize the station. Once done, a green dot will appear next to the station name
