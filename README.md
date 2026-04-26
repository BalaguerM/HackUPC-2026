# HackUPC-2026

## Project Purpose

This repository documents how to unlock suppressed Internal Forms Representation (IFR) options on systems using the InsydeH2O BIOS. Many manufacturers hide advanced BIOS settings, limiting user access to features that might affect stability or security.

## Why unlock hidden BIOS options?

- Access advanced settings for hardware configuration or system repair
- Enable features like virtualization, memory tweaking, or device toggles that aren’t available by default
- Troubleshoot limitations imposed by vendors

## How it Works

The general approach involves:

1. **Backing up your BIOS:** Always copy your device’s BIOS image before making changes, using software like flashrom or the OEM’s tools.
2. **Extracting IFR data:** Use tools like IFRExtractor to parse and view the structure of your firmware menus (IFR).
3. **Identifying suppression logic:** Scan for settings blocked by "Suppress If", "Gray Out If", or similar conditions in the IFR output.
4. **Modifying variables or patching:** Use UEFITool or a hex editor to note the "Supress If" conditions, removing or bypassing suppression checks.
5. **Booting with SREP:** Create a config file, and with SREP, boot it up and use it.
6. **Entering BIOS Setup:** Confirm that previously hidden options are now visible and accessible.

## Risks and Warnings

- Modifying firmware is inherently dangerous—bricking is possible if the wrong settings are changed or if flashing fails.  
- Always keep a backup of your original BIOS image and have a recovery method ready.  
- These operations may violate warranty or support agreements.

## Required Tools

- Firmware backup and flashing utilities (flashrom, FPT, or hardware programmer)
- IFRExtractor or Universal IFR Extractor for IFR parsing
- UEFITool or a hex editor for modifying the BIOS image
- A compatible system with InsydeH2O BIOS

## Additional Resources

- [InsydeH2O official site](https://www.insyde.com/products/firmware)
- [IFRExtractor by LongSoft](https://github.com/LongSoft/IFRExtractor)
- [UEFITool](https://github.com/LongSoft/UEFITool)
