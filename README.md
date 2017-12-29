# DeSmuME-Reloaded

DS emulator with WiFi support === Author : JackoboLeChocobo



# SETUP FOR LINUX

DeSmuME Classic Version :
- cd desmume/src/frontend/posix
- ./autogen.sh
- ./configure --enable-glx --enable-openal --enable-glade --enable-wifi
- make
- cd gtk

After compilation of the project, run the following command to use the libpcap functions in standard user mode :
- sudo setcap cap_net_raw,cap_net_admin=eip ./desmume

Place your bios files in the Bios directory of your choice :
- ARM7 filename : biosnds7.bin
- ARM9 filename : biosnds9.bin
- Firmware filename : firmware.bin

Example for using DeSmuME after all these steps :
- desmume --bios-arm9 "/your_path_of_the_bios_directory/biosnds9.bin" --bios-arm7 "/your_path_of_the_bios_directory/biosnds7.bin" --firmware-path "/your_path_of_the_bios_directory/firmware.bin" --firmware-boot 1


DeSmuME RetroArch Version (64-bit version) :
- cd desmume-libretro
- make -f Makefile.libretro

A file named "desmume-libretro.so" will be created. Place it in the core directory of your RetroArch setup.

After that, run the followings command to use the libpcap functions in standard user mode :
- sudo setcap cap_net_raw,cap_net_admin=eip /your_path_of_the_core_directory/desmume-libretro.so
- sudo setcap cap_net_raw,cap_net_admin=eip /your_path_of_the_retroarch_bin_directory/retroarch

Place your bios files in the System/Bios directory of your RetroArch setup, and in the Core Options choose Yes for "Use Bios Files" if you want to use the WiFi and restart RetroArch :
- ARM7 filename : NDS-bios-ARM7.bin ( originally named biosnds7.bin on the Web )
- ARM9 filename : NDS-bios-ARM9.bin ( originally named biosnds9.bin on the Web )
- Firmware filename : NDS-bios-Firmware.bin ( originally named firmware.bin on the Web )

To use this core on RetroArch, you can use this command line :
- /your_path_of_the_retroarch_bin_directory/retroarch -L /your_path_of_the_core_directory/desmume_libretro.so Your-Game.nds


# SETUP FOR WINDOWS

DeSmuME Classic Version :
- Download WinPcap here : https://www.winpcap.org/install/bin/WinPcap_4_1_3.exe
- Open the file "desmume\src\frontend\windows\DeSmuME.sln" in Microsoft Visual Studio ( tested for me on 2015 version )
- Build a Release project (tested for me a build of x64 version)


DeSmuME RetroArch Version :
- Not tested now

# TODO

- See for useful ameliorations to add on my DeSmuME version ( bug fixes and suggestions are welcome)
- Collaboration with StapleButter (MelonDS developper) and other people to add WiFi local support ( 

# History

29-Dec-2017 : Add libretro (RetroArch) support (64-bit version) 

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
