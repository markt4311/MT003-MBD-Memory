# MT003-MBD-Memory
64K/4M by 8 Memory compatible with RC2014

I wanted a memory board that could be used with 8Kx8 RAM or 512Kx8 RAM with a Z80 Board using an RC2014 compatible bus.

Mounting holes and header pins are matched to the MT002 modular backplane as the size and weight of the memory board may not be stable if mounted vertical in an RC2014 backplane.

Only the 64K build has been tested so far.

DIL Memory is fitted to both top and bottom side of the board to allow eight memory devices to fit within 102mm x 102mm pcb. Single in line round pin IC socket strip is used to allow soldering sockets for both sides of the assembly. Soldering of these connectors should alternate between top and bottom side of the pcb and work across the board from one dge towards the other, to allow access to solder both sides of the board.

Soldered links are required for power to 28 pin 8Kx8 Memory.

3.6v Battery back up can be connected at PL4. If a battery is not connected then Vbatt should be grounded to allow U12 to release reset.

The write protect switch S1 disconnects /WR from the lowest addressed RAM only. (This is needed to allow simulating ROM at the lowest address, most Sord M5 games will write over this memory without write protect.)

UNTESTED OPTIONS.

Links can be selected to power U1 direct from Vcc instead of SRAM_VCC for the case where U1 is 512Kx8 EPROM type SST39SF040.

Up to eight 512Kx8 memory devices can be fitted to a total of 4Mx8.

U9A, U10A, U11 could be used to enable or disable a separate memory board to support simple CP/M 2.2 boot ROM switching.

U9A, U10B, U11, U14, U15 provide memory mapping, copied from Sergei Kiselev Zeta 2 and supported by ROMWBW. Only U1 and U2 required to support ROMWBW.

U1 could be mounted as a ZIF socket, but this may prevent mounting of sockets for U5 and U6.

Links could be added in unused positions of PL2 to bypass the memory mapping for use with Z180 or other processors with a larger address space.

It may be possible to stack two memory modules to provide D0-D7 and D8-D15 to experiment with processors using a 16 bit data bus, additional link may be needed for high and low byte selection.

Power fail can be detected from Vcc or unregulated supply and option to generate NMI.

Enable, Page_Reset and Page_en are available on user pins.
