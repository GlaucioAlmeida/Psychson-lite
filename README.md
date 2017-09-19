Phison 2251-03 (2303) Custom Firmware
========

Releases have the following items:
- `tools` -- these are the compiled binaries of all the tools.

Take note that the firmware patches have only been tested against PS2251-03 firmware version _1.03.53_ (which is for an 8K eD3 NAND flash chip). They may work for others, but be careful.

As long as you are using the correct firmware image for your controller version and NAND chip, there is no harm in downgrading to an earlier version (such as from 1.10.53).

**WARNING: This is experimental software. Use on unsupported devices, or even on supported devices, may cause loss of data, or even permananent damage to devices. Use at your own risk.**

## Getting Started
*See [Known Supported Devices](https://github.com/adamcaudill/Psychson/wiki/Known-Supported-Devices) for information on supported devices; use on an unsupported device may cause permanent damage to the device.*

## Dumping Firmware
Run DriveCom, passing in the drive letter representing the drive you want to flash, the path of the burner image you obtained, and the destination path for the firmware image:

    tools\DriveCom.exe /drive=E /action=DumpFirmware /burner=BN03V104M.BIN /firmware=firmware.bin

where `BN03V104M.BIN` is the path to the burner image, and `firmware.bin` is the resulting firmware dump.

## Flashing Custom Firmware
Run `DriveCom`, passing in the drive letter representing the drive you want to flash, the path of the burner image you obtained, and the path of the firmware image you want to flash:

    tools\DriveCom.exe /drive=E /action=SendFirmware /burner=BN03V104M.BIN /firmware=firmware.bin
