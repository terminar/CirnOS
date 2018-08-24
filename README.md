![CirnOS Logo](logo.png)
# CirnOS
CirnOS is an operating system for the Raspberry Pi built for the purpose of usability and simplicity. It provides a simple environment for running a Lua script that will run on the Raspberry Pi. It has no kernel or time management -- it is single threaded. You run your code on the device, and that is it.

CirnOS has only been tested on the Raspberry Pi Zero, but should work on the original Raspberry Pi and the Zero W.

Why use CirnOS when there's Raspbian?
-----
Raspbian is very bloated for what most Raspberry Pi users need. The average rPi is used for one specific embedded task. It does not need a kernel, or different protection levels, or an operating system that can take up hundreds of megabytes.

The workflow that Raspbian creates is also rather clunky. It requires the user to plug in a keyboard, mouse and screen into their Raspberry Pi to program and configure it, while the project that the rPi is used for might not need any of these peripherals.

It makes sense to have a lightweight, extensible system that allows a user to treat the rPi as an embedded device and edit its scripts directly from their computer.

Current Bugs
-----
Currently Lua is not configured to only provide functions that CirnOS supports, meaning that a user might be able to call functions that break CirnOS.

Using CirnOS
-----
- Format your rPi's SD card as FAT32, using a tool such as SD Association's SD Memory Card Formatter <https://www.sdcard.org/downloads/formatter_4/>.
- Make sure the root directory in the SD Card is empty, and that the SD Card has only one volume.
- Copy all files from ROOTDIR into the root of the SD Card.
- Copy kernel.img from OBJ into the root of the SD Card.
- Edit main.lua to control the rPi.

Building
-----
CirnOS currently can only be built on Mac and Linux devices. It requires an installation of Newlib for ARM, which can either be built by yourself with a bit of configuration or installed through a package such as libnewlib for Debian. Run the build.sh script to build kernel.img, configuring it as needed.

Why 'CirnOS'?
-----
CirnOS was built for use in my virtual pet project. This project was originally going to use 9front as its operating system, but I decided that 9front was too excessive for the tasks I needed my virtual pet to do. When I was using 9front it made sense to name my virtual pet after the mascot of the 9front operating system, the Touhou character Cirno. CirnOS is a portmanteau of Cirno and OS.

This may alienate some Touhou fans, but to differentiate CirnOS from the Touhou character, the preferred pronounciation of CirnOS is 'Sernos'.

Todo
-----
- Sandbox and test Lua.
- Make Lua wrappers for bcm2835 library.
- Replace Lua interpreter with LuaJIT for speed.
- Add a graphics library for HDMI.
- Create plugins for IDEs to abstract away CirnOS (Like Arduino).
- Add WiFi and HTTP server library.
- Add USB connection library.
