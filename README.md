# Phison PS2303 (PS2251-03) framework

This project's goal is to turn PS2303-based USB flash drive into a cheap USB 3.0 development platform (i.e. fast USB 3.0 to FPGA bridge).
Check [project's wiki](https://github.com/flowswitch/phison/wiki) for more information.

## Required build tools

[SDCC](http://sdcc.sourceforge.net/)
[SCons](http://www.scons.org/)

## Build

Build [PyScsi](https://github.com/flowswitch/pyscsi) (or get [prebuilt Win32 version](https://github.com/flowswitch/pyscsi/releases/download/v1/PyScsi_win32.zip)).  
Place PyScsi.dll into host/ directory.  
Build test.btpram in mcu/ (execute 'scons' there)

## Prepare USB stick

A PS2303-based USB stick must be in BootROM mode to be able to load and run custom code. This can be achieved in several ways:

1. Use host/go_isp.py script to reboot PS2303 from normal mode to BootROM (simplest, temporary)
2. Disrupt NAND probing at power up shorting some DATA lines with tweezers (temporary)
3. Desolder NAND completely (permanent)
4. Erase NAND firmware (permanent)

## Run

Use host/load.py script to load and run test.btpram, observe LED/communicate with the code.

# Licence

Public domain
