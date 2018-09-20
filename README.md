# pegasus12-configs-only
Just config.h and config_adv.h

Get current running printer config (Note: Must have eeprom enabled) 

==== EEPROM GCodes ====

    M500 Store current settings in EEPROM for the next startup or M501.
    M501 Read all parameters from EEPROM. (Or, undo changes.)
    M502 Reset current settings to defaults, as set in Configurations.h. 
         (Follow with M500 to reset the EEPROM too.)
    M503 Print the current settings – ''Not the settings stored in EEPROM.''

- Connect to printer and issue M503
	- In Octoprint click on terminal, tick supress temp messages
	- copy this to a file and cleanup with vi:  :%s/Recv/\r&/g


Following are summary notes from Pegasus Firmware guide.  This will allow us to flash the printer from Octoprint

PC/MAC setup:
- Download the arduino software
	- Go to www.arduino.cc
	- Click on “Download”
	- Download the latest - 1.8.7 for mac as of 9/17/2018
	- Install it.
- Open the Arduino software
	- Click on the Tools tab, then board and select “Arduino Mega 2560”. 
	- Go to File -> Preferences and then select Show verbose output during -> compilation.
	- go to Tools - > Manage Libraries - search for U8glib
		- install the latest 1.19.1.

## Prep and compile your new Marlin firmware

- Download the latest Marlin and extract
- Modify configuration.h and configuration_adv.h for your printer (or copy from my repo)
- Re-open the arduino software
	- Click File
	- Open 
	- Browse to the latest firmware you prepped and select the .ino file 
		Marlin.ino
- Now that we have our firmware loaded click on Sketch then Verify/Compile, if you do not get any errors and see “Done Compiling” at the bottom then we can grab the hex file.  
	-  The hex file will be in the build directory, do not pick the bootloader version.

## Install firmware updater in octoprint

    Click the wrench icon in the top right corner and configure the settings for the plugin
    Either click the 'Browse' button to upload a file, or provide a URL to a file
    In advanced add the following gcode (reload defaults, set old z offset from m503, save to eeprom, display success)
	M502; M851 Z-.9; M500; M117 Firmware updated.
    Click the 'Flash from' button
    Wait for the flash to complete
    Run a G28 and G29 command to verify operation and bed dimensions

	
