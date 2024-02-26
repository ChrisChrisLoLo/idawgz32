# idawgz32

> A mechanical keyboard, in _this_ economy??

An experimental ultraportable pocket keyboard that uses low profile SMD mouse switches (EVQP0N02B) to achieve a compact form factor (8mm thick) while still being viable as a daily use keyboard (85+ wpm). Entire PCBA can be produced by JLCPCB. Uses 3D printed keycaps.

![a photo of an idawgz32](https://raw.githubusercontent.com/ChrisChrisLoLo/idawgz32/main/images/PXL_20240225_225159875.jpg)

# Status
v0.0 PCBs are working! A pcb produced from the files should work.

Disclaimer is that this design has very low tolerances for its key switches. You will likely need a 3D printer such as a Bambu Lab A1/A1 mini/P1P/P1S and set the slicing layer resolution to 0.08mm. Printers like the Prusa i3/mini may also work, but have not been tested.

# About
I hit the limit as how small I could go with choc switches. For my bunchiez40 and modkipz40, I used kailh mute switches as a smaller alternative. While a good start, these switches are both fairly tall and not super comfortable to type on directly. This board alternatively uses SMD EVQP0N02B switches from LCSC, which lowers the board height considerably, and reduces manual assembly required. This board also uses 3D printed buttons, which makes keypresses more comfortable.

More details about my research on mouse switches and experience with the idawgz32 can be found here: https://chrischrislolo.github.io/orthoLabLogs/idawgz32.html

Case files include 3MF files, STEP files that include the top case housing, as well as the buttons.

![a idawgz32](https://raw.githubusercontent.com/ChrisChrisLoLo/idawgz32/main/images/PXL_20240225_201119535.jpg)


# Case
The case files can be found in the `case` directory. There is either the inverted rails or simple rails model to choose from. The simple rails model can be cnc'd, but has a rare tendency to have the buttons stick when pressed at a weird angle (1/1000 presses, as a rough guage of frequency). The inverted rails model has less of this issue, but cannot be cnc'd due to its sharp edges. I currently daily drive with the simple rails model.

3D printed cases can and should use the finest resolution possible on your printer, and ideally should use a higher end printer due to it's low tolerances. The models have been tested to work with the Bambu lab A1 and P1S at a layer height and detail setting of 0.08mm (extra fine). It's recommended to use a high quality and/or a newer printer.

Lubricating the case rails with something like krytox 205g0 is recommended, especially when using a CNC aluminum case. 

## PCB
You can find the PCB source files in the `pcb` folder. The BOM files can be found in this folder.

![idawgz32 pcb](https://raw.githubusercontent.com/ChrisChrisLoLo/idawgz32/main/images/PXL_20240225_224453990.jpg)

## Directory Structure
- `case`
    You can find the files you need in this folder to print out a case for the keyboard
- `drafts`
    Stores any ergogen or intermediate information used in making the case
- `pcb`
    Kicad project relating to the project. Contains the BOM, placement files, and gerbers
   
## BOM
- 1 PCBA
  - The PCB will include all electrical parts required, including switches.
- 1 Aluminum CNC upper case or 3DP upper case
- 40 3D printed buttons
- 8 3mm M1.6 screws (go for flathead for a more flush fit, though other head types should also work)
- 4-8 (ideally 8) 1-2mm bumpons (something like Sj5302 is a good place to start)

## Assembly
Flash the pcb via QMK (see below section). Bootmagic is enabled, so using the top left key to flash from here on out is doable.

Pop the 3D printed buttons/keycaps into the case, and make sure they don't stick and can freely move up and down. If they do stick (e.g. need noticable force applied to pop out), confirm that you're printing at the finest detail setting. All keys need to be flush against the case. Once the switches are in place, over lap the pcb over the case. Gently press the pcb to make sure a button isn't pressed down.

Optionally wrap the board with a rubber band to hold it in place and flip it over to validate everything. Then gently press every button to make sure if it can actuate. If a button is very sticky, reprinting or sanding may be required. If there's slight friction on the keys return, this should slowly go away as the keyboard is broken in. If there's a button that won't actuate, it's possible that the button is misaligned. Flip the board back around, remove the rubber band and pcb, and make sure the problematic key is flush against the case. Place back pcb around and test until all keys properly acutate.

Then turn the keybard around one last time so the pcb is facing upwards. Screw on the screws and test one last time.

Finally, place on the rubber bumpons

## Firmware
QMK Firmware can be found here
https://github.com/ChrisChrisLoLo/vial-qmk/tree/sporewoh/keyboards/sporewoh/idawgz32
