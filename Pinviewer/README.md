# Pinviewer for external Board for Colorlight i9 v7.2

(c) 2024 by kittennbfive - CC BY-NC-SA 4.0  
  
ALPHA VERSION! - INCOMPLETE! - Feedback welcome  

## Why?
Well, the external board is technically speaking Open Source but i would put this in quotes as the only(?) [schematic](https://github.com/wuxx/Colorlight-FPGA-Projects/blob/master/schematic/i5-i9-extboard.pdf) i found does not match for the FPGA-pins for the i9. There is a [pinout](https://github.com/wuxx/Colorlight-FPGA-Projects/blob/master/doc/i9_v7.2_pinout.png) available but it is a picture/drawing, so non-interactive. In theory this is enough to use the board, but it is not very convenient (for me at least). So i made this tool...

## Disclaimer
Please note that i am *really* bad with HTML/CSS/Javascript. This tool mostly works for me (tested with Firefox 115.8 ESR), but would definitively benefit from some work from somebody more skilled then i am with web-stuff (PR welcome!). Also some informations are missing, see below.

## What is implemented/available
You can (with Javascript enabled) click on any pin to see some details, including if this pin can be used as a differential pair (together with another pin that is specified too). If you enable it the other pin will be highlighted too to quickly see where it is.  
If enabled you can "hover" over a connector to see a "zoom" with the pinout.  
The pin-designators are those from the Lattice LFE5U-45F-6BG381C and can/must be used inside a `constraints`-file for Yosys/Nextpnr (and maybe the proprietary Lattice toolchain, i don't know).

## What is missing
Some pins of the FPGA are also connected to the microcontroller on the external board, these informations are currently not shown on the Viewer. Also there is a LED on one pin and of course the connections that are "internal" to the i9, ie between the FPGA and the Ethernet-PHYs/DRAM/..., are not available on the Viewer as it is not its purpose to document these. You may want to consult the (official?) [documentation](https://github.com/wuxx/Colorlight-FPGA-Projects/blob/master/colorlight_i9_v7.2.md).

## Verification
The provided pinout has been verified on real hardware using multiple UART inside the FPGA. Please note that at least one pin (H18) does **not** work as an output, there must be a conflict (ie two outputs "fighting" against each other) with some other part, probably the microcontroller.
