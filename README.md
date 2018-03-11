# pegasus12-configs-only
Just config.h and config_adv.h

Following are summary notes from Pegasus Firmware guide.  This will allow us to flash the printer from Octoprint

PC/Mac setup:
- If you haven’t already downloaded the arduino software goto www.arduino.cc, click on “Download”, then click on “Previous Releases” then Download Arduino 1.0.6 (Don’t get a newer version, get 1.0.6) that matches your Operating System. For this set of instructions we are going to use the Windows version, but other operating systems should be similar. After Downloading the Arduino 1.0.6 software go ahead and install it.
- Open the Arduino software, Click on the Tools tab, then board and select “Arduino Mega 2560 or Mega ADK”. 
- In the Arduino software: go to File -> Preferences and then select Show verbose output during -> compilation.
- Next Unzip the firmware file that you downloaded earlier
  - https://drive.google.com/file/d/0B80A_woXoRWdQ2NMSzhQdi1RODg/view
- Now that we have extracted our firmware you should see the following in the Firmware Folder: “u8glib_arduino_v1.15”, Unzip the file, then inside of the “u8glib_arduino_v1.15” folder you will see a folder called “U8glib” we need to copy the U8glib folder into our Arduino/Libraries folder, to do this right click on the U8glib folder and click copy. Now we need to paste this folder into the Arduino Libraries. To do this your Path may be different, but it will be something similar to this: C:\Program Files (x86)\Arduino\Libraries. Once you are in the Libraries folder right click on an empty space and click Paste. 

- Now restart your computer then open the arduino software again, click File, then Open, browse to the firmware you downloaded and unzipped and select the file shown to match your configuration below:
	12“ Pegasus: Marlin1_0_2_Pegasus12.ino
- Now that we have our firmware loaded click on Sketch then Verify/Compile, if you do not get any errors and see “Done Compiling” at the bottom then we can grab the hex file.  
	- The program will show you lots of data. At the last lines, you will find the path to the .hex file.
	- ex: C:\Users\<user>\AppData\Local\Temp\buildxxxx.tmp\Marlin-1.1.0-RC3_12_pegasusBLTouch.cpp.hex

