This firmware has to be uploaded to OLIMEXINO-32u4 in order to use it as an iCE40 programmer.

This firmware can be uploaded via Arduino IDE. To compile it use SPIFlash 2.2.0 library for 
Winbond Flash Memory by Prajwal Bhattaram - Marzogh.

To load this library via Internet go to Sketch -> Include Library -> Manage Libraries. Refer
to the pictures in this folder for more information on the library installation procedure.

## BUT+RST to start USB to Serial
Hold BUT down until last restart, i.e. for a rather long time. Think of BUT as a shift-button to
RST, but that must be held down a long time after RST has been released.

This is useful when developing FPGA-projects that use serial communication with the computer 
that you used to program it with. You don't have to buy an extra USB to serial converter or 
use an extra USB cable or port.

In order to use it as a programmer for FPGA you have to press RST without BUT.

I use it with [Apple I](https://github.com/alangarf/apple-one) in Verilog. Connect D0 to GPIO7 
and D1 to GPIO5 for Olimexino-32U4 and iCE40HX8K-EVB, respectively. CTS (GPIO9) not yet 
implemented. Note: You must also edit rtl/boards/olimex_ice40hx8k/apple1_hx8k.v so that PS/2 
is excluded, and make and program the iCE with the new apple1.bin.

To send files: Transmit delay: 200 msec/char, 700 msec/line.
