# pegasus12-configs-only
Just config.h and config_adv.h

Following are summary notes from Pegasus Firmware guide.  This will allow us to flash the printer from Octoprint

PC/Mac setup:
- Download the arduino software
	- Go to www.arduino.cc
	- Click on “Download”
	- Click on “Previous Releases” and download Arduino 1.0.6 (Don’t get a newer version)
	- Install it.
- Open the Arduino software
	- Click on the Tools tab, then board and select “Arduino Mega 2560 or Mega ADK”. 
	- Go to File -> Preferences and then select Show verbose output during -> compilation.
- Next download and unzip the firmware file from Makerfarm's guide (this is old but it has the graphics U8 libraries)
  	- https://drive.google.com/file/d/0B80A_woXoRWdQ2NMSzhQdi1RODg/view
- In the Firmware Folder extract “u8glib_arduino_v1.15”
	- inside you will see “U8glib”, copy this to C:\Program Files (x86)\Arduino\Libraries
- Your env is all prepped to compile your new firmware

## Prep and compile your new Marlin firmware

- Download the latest Marlin and extract
- Modify configuration.h and configuration_adv.h for your printer (or copy from my repo)
- Re-open the arduino software
	- Click File
	- Open 
	- Browse to the latest firmware you prepped and select the .ino file 
		Marlin.ino
- Now that we have our firmware loaded click on Sketch then Verify/Compile, if you do not get any errors and see “Done Compiling” at the bottom then we can grab the hex file.  
	- The program will show you lots of data. At the last lines, you will find the path to the .hex file.
	- ex: C:\Users\<user>\AppData\Local\Temp\buildxxxx.tmp\Marlin-1.1.0-RC3_12_pegasusBLTouch.cpp.hex

