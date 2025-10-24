# Royal Kludge R65 firmware (Wired ISO version)

## Overview

The Royal Kludge R65 is a 66-key RGB backlit mechanical keyboard with Chartreuse, Brown, or Blue switches. It offers a gasket structure for a soft typing experience, knob volume adjustment, ergonomic design, hot-swappable keys and QMK support.

I acquired this beauty from MercadoLibre and sadly RK official site no longer provide a functional software, so I remapped both ISO and RGB matrix layout based on QMK documentation. This batch also seems not to provide VIA, VIAL, kanata (Linux), RK software support, although Chromium based browsers manage to detect it (Firefox needs WebHID extension installed) and ```VIA_ENABLE = yes``` entry is set in rules.mk.
This version corresponds to 342d:e480 device, most likely lastest Latinoamerican vendor releases this year AFAIK.

*Major changes are subject to keycodes Deprecation Notices made by QMK as they mention on 11/2024 changelog and RGB matrix remap for assigning leds to respective keys. You are always encouraged to visit their [site](https://docs.qmk.fm/) for further customizing. Also you can always use this firmware as a rollback as long as it contains default settings with funtional knob, state leds, Mac layout, all 43 stock defined RGB animations properly working.*

Special thanks to @sdk66 for sharing the initial firmware files, @NieblaDev and @iamdanielv for fixing a major portion of the code. @qmk of course!

> [IMPORTANT] 
> This branch only contains files for the **wired ISO-layout** version of the Royal Kludge R65.
> **DO NOT** flash this firmware if your keyboard has wireless capabilities.
> **DO NOT** flash this firmware if you're unsure of your keyboard's variant/don't know much about keyboard modification.

### > Setting Up Environment

1. **Install QMK MSYS**  
   Download and install [QMK MSYS](https://msys.qmk.fm).

2. **Set Up QMK MSYS**  
   Open QMK MSYS and run the command:  
   ```bash
   qmk setup
   ```
   It may ask for confirmation and take a few minutes depending on network.
   A folder will be installed at `C:/Users/%USERNAME%/qmk_firmware`.

3. **Add Keyboard Files**  
   Download this repository and place the `rk/r65` folder into your `qmk_firmware/keyboards/` folder.

### > Compiling Firmware

1. **Compile the Firmware**  
   Run the following command in QMK MSYS:  
   ```bash
   qmk compile -j 0 -kb r65 -km iso
   ```
   *Note ```-j 0``` speeds up the job by enabling parallel threads.
   
2. **Locate the Firmware File**  
   Find the compiled `.bin` file in the root of the `qmk_firmware` folder.

### > Flashing Firmware

1. **Install QMK Toolbox**  
   Download and install [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases).

2. **Load the Firmware File**  
   Open QMK Toolbox as Admin and load the `.bin` file.

3. **Enter Bootloader Mode**  
   Reset the keyboard into bootloader mode. (Procedure below)

4. **Flash the Firmware**  
   Click 'Flash', then 'Exit DFU' once the flashing process is complete.

### > Entering Bootloader/DFU Mode

- **Option 1**: Hold the Reset switch on the PCB while connecting the USB cable.
- **Option 2**: Hold the Escape key while connecting the USB cable (this will also erase settings).
- **Option 3**: Press `Fn+Shift+Esc`. (Preferred)

## Known Issues

You tell me
