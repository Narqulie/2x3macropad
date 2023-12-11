# 2x3macropad

![2x3macropad](imgur.com image replace me!)

This is a tiny 2x3 macropad, with six keys in total, completely programmable with the VIA web interface. The hardware is handwired in a simple matrix, the chassis is 3D-printed and a special set of keycaps in in the works. 


* Keyboard Maintainer: [JHEAm](https://github.com/narqulie)
* Availability: Hardware oly available through special request

# Hardware info
* Microcontroller: ProMicro
* Diode Direction: COL2ROW
* Processor: ATmega32u4
* VIA support

## Matrix Pins
* Columns: D4, D0, D1
* Rows: B1, B3

## Layout
* 2x3 Matrix Layout:
  - [0, 0] (x: 0, y: 0)
  - [0, 1] (x: 1, y: 0)
  - [0, 2] (x: 2, y: 0)
  - [1, 0] (x: 0, y: 1)
  - [1, 1] (x: 1, y: 1)
  - [1, 2] (x: 2, y: 1)


# VIA configuration
To configure the macropad on VIA, plug in the pad and navigate to https://usevia.app.
Once there, goto settings, 

![settings](/via_setup/settings.png)

and enable the Design tab-option:
![design](/via_setup/design_tab.png)

If prompted, confirm the usage of the design tab: 
![design_confirm](/via_setup/confirm.png)

Then, navigate to the design tab, and click the "Import Keymap" button:
![load_json](/via_setup/load_json.png)
Load the [via.json](/via.json) file from this github repo into VIA, and confirm connection:
![confirm_connection](/via_setup/confirm.png)
The matrix of the keyboard should be visible in the design tab: 
![matrix](/via_setup/matrix.png)

Now head to the configure-tab and get configuring!

![configure](/via_setup/configure.png)

Select any of the keys and use the menu below to configure the key to your liking. All changes are instataneously saved to the keyboard and persist on the firmware even after unplugging the keyboard.

Via supports simple and complex special keys, as well as writing and recording macros on the fly. For more information on VIA, check out the [VIA documentation](https://caniusevia.com/docs/).

## Bootloader

If there is ever a need to access the bootloader of the Pro Micro, there are a few ways to do so.

* **Bootmagic reset**: Hold down the key at (0,0) in the matrix (the top left key on the pad) and plug in the keyboard
* **Physical reset button**: Briefly short the GND and RST pins on the Pro Micro, a paperclip works nice.
* **Keycode in layout**: Map QK_BOOT to a key in the layout, and press it to enter the bootloader.
