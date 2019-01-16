https://github.com/unixpunk/PlutoWeb/

Files: https://github.com/unixpunk/PlutoWeb/tree/master/plutoweb/images

Sequence:
1)	Reset halten und Reboot -> geht in den DFU Modus
2)	dfu-util -a boot.dfu -D boot.dfu
3)	reboot und Schritt 1 nochmals
4)	dfu-util -a firmware.dfu -D pluto.dfu
5)	fertig



The other way to flash the PlutoSDR is with the dfu utility. From the plutoweb/images directory run

sudo dfu-util -a firmware.dfu -D pluto.dfu

If you have issues after and it wont come back up you will need to flash boot.dfu

sudo dfu-util -a boot.dfu -D boot.dfu




dfu-util 0.9

These binaries are for Microsoft Windows 64-bit

They were built using MinGW-64 from MSYS2 with gcc 5.3.0,
for build instructions please see:
http://dfu-util.sourceforge.net/build.html

Source code:
https://sourceforge.net/p/dfu-util/dfu-util/ci/v0.9/tree/

dfu-util.exe requires libusb-1.0.dll. The shipped libusb-1.0.dll
is built from libusb 1.0.20 and can be replaced with another
version if desired.

dfu-util-static.exe has the libusb 1.0.20 code embedded and runs
without any libusb-1.0.dll.

Notes:
1. To work around a bug in gcc/mingw, a small patch was applied, see
   https://sourceforge.net/p/dfu-util/tickets/13/
2. The dfu-util-static.exe includes libusb that has been patched
   to work around a silicon bug in STM32F42X devices:
   https://github.com/axoloti/axoloti/blob/master/platform_osx/src/libusb.stdfu.patch

2016-02-11 Tormod Volden