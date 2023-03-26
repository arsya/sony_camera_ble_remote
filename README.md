# Sony Camera Bluetooth Remote

This project is inspired by coral's [freemote](https://github.com/coral/freemote) project, which implements sony BLE remote on NRF52840.
I wanted to do the same thing using micropython on ESP32 SoC, but having trouble with pairing dan bonding, which in not yet implemented.
Found another route by using nRF Connect App by [Nordic Semiconductor](https://www.nordicsemi.com/), available for Desktop (Windows), Android and IOS.

The xml in this project contains macros for nRF Connect App. It uses only the following remote command, in order to take picture.

| Code	    | Description     |
| --------- | --------------- |
| 0x0107	| Focus Down      |
| 0x0106	| Focus Up        |
| 0x0109	| Shutter Down    |
| 0x0108	| Shutter Up      |

### Macros

There are two xml files:
1. Capture.xml: to take picture.
2. Record.xml: to record video. 


### Steps

What you need to do is:
1. Install [nRF Connect App](https://play.google.com/store/apps/details?id=no.nordicsemi.android.mcp&hl=en).
2. Download Capture.xml/Record.xml and store it on your device.
3. Pair you camera with your device.
4. Open nRF Connect App
5. Connect to your camera from your nRF Connect App.
6. Tap on macros button (bottom right corner icon for Android App)
7. Tap on download button, and select Capture.xml/Record.xml file.
8. Run "Capture/Toggle Record" macro to test.

## Additional Info
Thanks to [Greg Leeds](https://gregleeds.com/reverse-engineering-sony-camera-bluetooth/) for reverse engineering these bluetooth remote commands.

| Code	    | Description     |
| --------- | --------------- |
| 0x0107	| Focus Down      |
| 0x0106	| Focus Up        |
| 0x0109	| Shutter Down    |
| 0x0108	| Shutter Up      |
| 0x0115	| AutoFocus Down  |
| 0x0114	| AutoFocus Up    |
| 0x026d20	| Zoom In Down    |
| 0x026c00	| Zoom In Up      |
| 0x026b20	| Zoom Out Down   |
| 0x026a00	| Zoom Out Up     |
| 0x0121	| C1 Down         |
| 0x0120	| C1 Up           |
| 0x010e	| Toggle Record   |
| 0x024720	| Focus In? Down  |
| 0x024600	| Focus In? Up    |
| 0x024520	| Focus Out? Down |
| 0x024400	| Focus Out? Up   |
