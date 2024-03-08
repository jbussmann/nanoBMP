# nanoBMP

| ![Front View](/nanoBMP_front.jpg) | ![Back View](/nanoBMP_back.jpg) |
|-|-|

This is my attempt at miniaturizing open source debugger hardware and with a PCB size of just 8x11mm what I claim to be tha world's smallest JTAG/SWD debugger for embedded microcontrollers. The debugger is built to be compatible with the [Black Magic Firmware](https://black-magic.org). It features an integrated GDB server providing full debugging funktionality as well as a bidirectional UART to USB bridge, both accessible through thir respective virtual serial port.

### Why would anyone design something like this?

To answer that let me tell you a bit about me and my history. When I studied Electrical Engineering and it was time to design my first PCB, we got a simple assignment: redraw this simple schematic of a simple circuit oround a small STM32 MCU, create the layout accordingly and finally solder the board. Additionally, we were given the option to modify the schematic as desired, as long as we stay within a set budget. An opportunity no one ever has to mention twice to me! Needless to say, I hit the budget in no time and when I realised the debugger (in the form of a full Nucleo Eval-Board) made up a quater of the budget I thought to myself: why waste all that money and most of the evaluation kit just for a debugger? If only I could embed my own debugger in the same way those Nucleo boads embed a ST-Link.

So I went down the rabbit hole and after watching a [russian Video](https://www.youtube.com/watch?v=irhgQCaBoGs) many times back and forth (thank you, automatic subtitle generator and translator), I decided this was doable. So I embedded my very own ST-Link onto my board which ist not much more than a MCU with a crystal and a power supply. However, this was only half a debugger and I also needed the ST-Link firmware. This proved to be easier said than done, as STM understandably doesn't make the bootloader for their debugger publicly available. This is required though, to be able to flash the main firmware, using theis debugger update tool. So I had to revert to questionable sources, but got it working after all. Of course I spent much more time on this then it was the intention, on the other hand I grew my understanding of debuggers by a huge amount. 
