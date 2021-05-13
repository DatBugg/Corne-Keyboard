
<h2 align="center">
  Corne Keyboard<br/>
</h2>


![forthebadge](https://forthebadge.com/images/badges/built-by-hipsters.svg) ![forthebadge](https://forthebadge.com/images/badges/powered-by-coffee.svg)


## Corne Keyboard proyect

Guide on how to assemble a corne keyboard based on my experience and in the order I do it.
In the process I made mistakes which I corrected so that they could avoid them.

## Parts
- PCB x2
- Diodes x42
- Case x2
- Keycaps x42
- Switches x42
- TRRS x2
- TRRS cable X1
- Pro Micro controllers X2
- Micro USB to USB A cable X1
- Reset button x2 (optional)
- Oled display 128x32 px  (optional)
- RBG LEDs x54 (optional)


## Tools

- Tin Welder (better if it has an adjustable temperature, use at 300 Cº)
- Screwdriver
- Tin (preferentemente 0.7mm)
- Flux (optional)
- [QMK Firmware](https://docs.qmk.fm/)
[Github QMK](https://github.com/qmk/qmk_firmware/tree/master/keyboards/crkbd)
- [Keymap](https://github.com/qmk/qmk_firmware/tree/master/keyboards/crkbd/keymaps)

## Assembling

 1. Test the Pro Micro Controllers.
 2. Solder to the PCB.
	 1. Pro Micro.
	 2. TRRS.
	 3. Reset Button.
 3. Make a bridge with a solder in the section of LEDs.
 4. Solder to the PCB.
	 1. Diodes.
	 2. Switches (between the switch and the PCB goes the upper part of the case).
 5. Test all switches.
 6. Solder to the PCB the LEDs, but first solder one and test.
 7. Place the bottom of the case with the spacers.

## Programming

 1. Run QMK Firmware
 2. On the console type
 ``` qmk setup ```
 ``` qmk compile -kb <keyboard> -km default ```
 Replace "keyboard" for "crkbd" (corne keyboard), and "default" by de layout you have chosen
 In my case it looks like this.
  ``` qmk compile -kb <crkbd> -km thefrey ```
  3. Now let`s flash the keyboard
 ``` qmk flash ```
  4. When the previous step finishes it will ask us to place the keyboard in DFU mode, 
For this we will first connect the left side of the keyboard to the pc and press the resset button (if they do not have it, make a bridge between the 2 holes where the button would go)
  5. When it's done, we type again
 ``` qmk flash ```
 6. We connect the right side and put it back in DFU mode.

Ready, to connect the keyboard to the pc use the left side.

My layout has a little change between the CTRL and SHIFT
To edit the keymap, simply open keymap.c with a text editor and modify the values ​​within the grid. 
