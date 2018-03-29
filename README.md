ESP Easy Flasher
------------

![ESP Easy Flasher GUI](Screenshot.png)

INTRO
------------
**ESP Easy Flasher** is a wrapper for the great [ESPTOOL.exe](https://github.com/igrr/esptool-ck/blob/master/README.md) and Power Shell to be able to easily flash and program ESP8266 units with the firmware [ESP Easy](https://www.letscontrolit.com/wiki/index.php/ESPEasy). All needed files are included in the EXE file, just download it and place it where you want it. It will extract needed file structure and missing files automatically. The idea behind the app is to make the flashing and setup of ESP Easy FW as stream lined as possible. It's still a very early stage but should hopefully be functional for most use-cases.

FLASH FEATURES
------------
```diff
+ Flash ESP8266 (+ESP8285) using embedded ESPTOOL.exe [0.4.12]
+ Use maximum baud rate if wanted
+ Use forced DOUT if wanted
+ Monitor serial (COM) port using embedded plink.exe
- Erase flash (NOT IMPLEMENTED)
- Scan for ESP model + size of mem (NOT IMPLEMENTED)
```

POST FLASH FEATURES (for ESP Easy 2.0.0+)
------------
```diff
+ NO NEED FOR AP MODE setup: set Unit name, number, admin password, Wifi settings, IP, right after flash
+ Activate and upload rules (DEPENDING ON THE CONNECTION TO THE UNIT THIS MIGHT TAKE SOME MINUTES DUE TO LATENCY)
```

EXTRA INFORMATION
------------
* **ONLY WINDOWS** is supported (Windows 10, Windows 8.1, Windows 8, Windows 7) since it rely on PowerShell v2+ to serial communicate with the units.
* **Agency FB** is the font used within the app, if not present the app will kindly ask you to drag-and-drop the two font files found in the APP_DATA folder to the FONTS folder (automatically opened).
* **Admin rights** are needed to be able to get COM port names (driver names).
* **BIN files** need to be placed in the BIN folder (might change in the future but I plan to automatically download new releases from GitHub)
* **Rules (txt) files** need to be placed in the Rules folder.
* **Log files** for each flash will be placed in the Log folder.
* **Debug log** is created by: save settings and open the ini file, change debug level 0 to 1, restart app and a bug log file will appear in the same place as the exe. [Debug logs are sent here](https://dbinbox.com/harkrank), but please add information (email, name etc.) in the text file prior to upload!
* **ERROR handling** if the flash tool is telling you that an error has occurred, a standard test is to simply reset the unit (if the unit has a switch for this, use that one, else disconnect the cable) and then try again. Flashing over serial is not an exact science.
* **Post flash handling** after a successful flash you can use the tool to also program the unit over the serial connection. Using the text input fields in the GUI (unit info and wifi settings) you can make the ESP login to your network without the need for it to be connected using the access point mode. BUT, some units have a hard time rebooting after flash (the default way is that the flash tool will make the unit reboot after successful flash). To fix this I have added the functionality of having the application pause right after the flash and prior to the post flash sequence, this allows you to manually reboot/reset a unit that doesn't respond to the serial communication automatically.

I plan add more features on a weekly basis. Thanks for all the feedback!


LEGEND
------------
```diff
+ Green is a feature already implemented
- Red is on the todo-list
```

DISCLAIMER
------------
* **GUI** is messed up on Windows 10 (at least) compared to Windows 7 (which I compile the exe on). I will try to fix this in future releases, BETA, but as of now I focus on the core function. The main problem comes from W10 willingness of showing the interface with zoom activated. Reverting it to 100% fixes some of the messiness.

