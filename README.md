# DeSmuME-Reloaded

DS emulator with WiFi support

# SETUP FOR LINUX

DeSmuME Classic Version :
- cd desmume/src/frontend/posix
- ./autogen.sh
- ./configure --enable-glx --enable-openal --enable-glade --enable-wifi
- make
- cd gtk

After compilation of the project, run the following command to use the libpcap functions in standard user mode :
- sudo setcap cap_net_raw,cap_net_admin=eip ./desmume

Example for using DeSmuME after all these steps :
- desmume --bios-arm9 "/home/test/Documents/MyBios/biosnds9.bin" --bios-arm7 "/home/test/Documents/MyBios/biosnds7.bin" --firmware-path "/home/test/Documents/MyBios/firmware.bin" --firmware-boot 1

DeSmuME RetroArch Version :
- cd desmume-libretro
- make -f Makefile.libretro

A file named "desmume-libretro.so" will be created. Place it in the core directory of your RetroArch setup.

# SETUP FOR WINDOWS

DeSmuME Classic Version :
- Download WinPcap here : https://www.winpcap.org/install/bin/WinPcap_4_1_3.exe
- Open the file "desmume\src\frontend\windows\DeSmuME.sln" in Microsoft Visual Studio ( tested for me on 2015 version )
- Build a Release project (tested for me a build of x64 version)

DeSmuME RetroArch Version :
Not tested now

# TODO

- See for useful ameliorations to add on my DeSmuME version ( bug fixes and suggestions are welcome)
- Collaboration with StapleButter (MelonDS developper) and other people to add WiFi local support

# History

16-Dec-2017 : Fourth version with WiFi support working with DWC project on Linux and Windows versions

13-Dec-2017 : Third version with WiFi support working with DWC project
- Desmume version 0.9.12 svn
- Firmware can be set via command-line

13-Dec-2017 : Second version with WiFi support working with DWC project
- Desmume version 0.9.11 svn
- Firmware can be set via command-line and GTK mode

12-Dec-2017 : First version with WiFi support working with DWC project
- Desmume version 0.9.7 svn r3947
- Firmware can be set via command-line and GTK mode
- Bug fixes on loading and saving .dfc files
