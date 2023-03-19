# PicoSystem_InfoNes a NES emulator for the Pimoroni PicoSystem RP2040 gaming handheld
Now you can play Nintendo NES games on the [Pimoroni PicoSystem](https://shop.pimoroni.com/products/picosystem) RP2040 gaming handheld.

![image](https://github.com/fhoedemakers/PicoSystem_InfoNes/blob/master/assets/PicoSystem.jpg)

Click on image below to see a demo video.

[![Video](https://img.youtube.com/vi/4VYKSMvYWc8/0.jpg)](https://www.youtube.com/watch?v=4VYKSMvYWc8)

This is a work in progress, and still has lots of things todo:

- Fix colors that are somewhat off.
- Sound has to be implemented. Will be a challenge since the PicoSystem has as simple Piezo buzzer/speaker which has not the capabilities for generating proper sound from the NES. 
- Code has to be cleaned up. Uses parts of the [PicoSystem library](https://github.com/pimoroni/picosystem).
- Looking whether it is possible to bundle the executable with a game from the public domain.
- Companion App in Microsoft Windows for uploading roms to the handheld.
- Keep the emulator runnning at the correct speed.

### flashing the PicoSystem
- Download **PicoSystem_InfoNes.uf2** from the [releases page](https://github.com/fhoedemakers/PicoSystem_InfoNes/releases/latest).
- Connect PicoSystem using an USB-C cable to your computer. Make sure the PicoSystem is switched off.
- Push and hold the X button then the power-on button. Release the buttons and the drive RPI-RP2 appears on your computer.
- Drag and drop the UF2 file on to the RPI-RP2 drive. The PicoSystem will reboot and will now run the emulator.

## Button maps

- Y: SELECT
- X: START
- Y + X: Reset

## Uploading Roms
Load roms by setting the device in BOOTSEL mode. (Connect to computer then Hold X and power on device)
The ROM should be placed at address 0x10080000, and can be  transferred using [picotool](https://github.com/raspberrypi/picotool).
```
picotool load foo.nes -t bin -o 0x10080000
```

## Screen Resolution
The original Nintendo Entertainment System has a resolution of 256x240 pixels. The PicoSystem has a resolution of 240x240 pixels. Therefore, on the PicoSystem the first and last 8 Pixels of each horizontal line are not visible.

## Credits
InfoNes is programmed by [Jay Kumogata](https://github.com/jay-kumogata/InfoNES) and ported for DVI output to the Raspberry PI Pico by [Shuichi Takano](https://github.com/shuichitakano/pico-infones). I used the port of Shuichi Takano as a starting point for this project.
