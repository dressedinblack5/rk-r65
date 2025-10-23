# Royal Kludge R65 firmware (Wired ISO variant)

![Royal Kludge R65 Keyboard](via-r65.png)

## Overview

The Royal Kludge RKR65 is a 66-key RGB backlit mechanical keyboard with Chartreuse, Brown, or Blue switches. It offers a gasket structure for a soft typing experience, knob volume adjustment, ergonomic design, hot-swappable keys and QMK support.

I acquired this beauty and sadly RK official site no longer provide a functional software, so I remapped both ISO key and RGB matrix layout based on QMK documentation.

Special thanks to @sdk66 for sharing the initial firmware files, @irfanjmdn and @iamdanielv for fixing a major portion of the code!

> [IMPORTANT!] 
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
   A folder will be installed at `C:/Users/%USERNAME%/qmk_firmware`.

3. **Add Keyboard Files**  
   [Download this repository](https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/irfanjmdn/r65/tree/master/rk/r65) and move the `rk/r65` folder into your `qmk_firmware/keyboards/` folder.

### > Compiling Firmware

1. **Compile the Firmware**  
   Run the following command in QMK MSYS:  
   ```bash
   qmk compile -j 0 -kb r65 -km iso
   ```
   
2. **Locate the Firmware File**  
   Find the compiled `.bin` file in the root of the `qmk_firmware` folder.

### > Flashing Firmware

1. **Install QMK Toolbox**  
   Download and install [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases).

2. **Load the Firmware File**  
   Open QMK Toolbox as Admin and load the `.bin` file.

3. **Enter Bootloader Mode**  
   Reset the keyboard into bootloader mode.

4. **Flash the Firmware**  
   Click 'Flash', then 'Exit DFU' once the flashing process is complete.

### > Entering Bootloader/DFU Mode

- **Option 1**: Hold the Reset switch on the PCB while connecting the USB cable.
- **Option 2**: Hold the Escape key while connecting the USB cable (this will also erase settings).
- **Option 3**: Press `Fn+Shift+Esc`.

## Known Issues

You tell me
