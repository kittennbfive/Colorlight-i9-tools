# Pinviewer for external Board for Colorlight i9 v7.2

(c) 2024 by kittennbfive - CC BY-NC-SA 4.0 - NO WARRANTY! - Feedback welcome!  

## Why?
It's all about convenience... There is a [schematic](https://github.com/wuxx/Colorlight-FPGA-Projects/blob/master/schematic/i5-i9-extboard.pdf) for the external board (*Caution*: While the FPGA-pins seems to match reality for i9, the location-indications (??) like "PR47C" do not match!), but it is not interactive, do not highlight differential pairs/pins, ... So i made this tool...

## Disclaimer
Please note that i am *really* bad with HTML/CSS/Javascript. This tool mostly works for me (tested with Firefox 115.8 ESR), but would definitively benefit from some work from somebody more skilled then i am with web-stuff (PR welcome!). And as usuallly this stuff comes WITHOUT ANY WARRANTY - use at your own risk.

## What is implemented/available
You can (with Javascript enabled) click on any pin to see some details, including if this pin can be used as a differential pair (together with another pin that is specified too). If you enable it the other pin will be highlighted too to quickly see where it is.  
If enabled you can "hover" over a connector to see a "zoom" with the pinout.  
The pin-designators are those from the Lattice LFE5U-45F-6BG381C and can/must be used inside a `constraints`-file for Yosys/Nextpnr (and maybe the proprietary Lattice toolchain, i don't know).

## What is missing
The connections that are "internal" to the i9, ie between the FPGA and the Ethernet-PHYs/DRAM/..., are not available on the Viewer as it is not its purpose to document these. You may want to consult the (official?) [documentation](https://github.com/wuxx/Colorlight-FPGA-Projects/blob/master/colorlight_i9_v7.2.md).

## Verification
The provided pinout has been verified on real hardware using multiple UART inside the FPGA. Please note that at least one pin (H18) does **not** work as an output as it is also connected to UART2_TX from the microcontroller on the external board.
