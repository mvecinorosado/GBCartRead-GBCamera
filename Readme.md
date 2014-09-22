GBCartRead - Gameboy Cart Reader
By [insideGadgets](http://www.insidegadgets.com) / support@insidegadgets.com
Contributor - Marcos Vecino Rosado - http://www.marcosvr.com

GBCartRead is an Arduino based Gameboy Cartridge Reader which uses a program or python script to interface with the Arduino. GBCartRead allows you to dump your ROM, save the RAM and write to the RAM.


REQUIREMENTS
--------------------
- Arduino (UNO)
- 2 x 74HC595 Shift Registers
- 27 x 470 Ohm Resistors (R1-R16, R19-R20, R21-R28, R31). 
  to have a high resistance already. These resistors would be for safety purposes only.
- 4 x 10K Resistors (R17, R18, R29, R30)
- All resistors are optionals
- Gameboy Cartridge Adapter


HOW TO USE
----------------
Note: It is important to insert your Gameboy Cartridge before you plug in your Arduino as you may experience RAM data loss if you insert when the Arduino is on.

--- PYTHON PROGRAM ---
1. Upload "GBCartRead_v1.4.2.pde" to the Arduino.
2. Download and install Python 3.2 (http://www.python.org/download/) and pySerial (http://pypi.python.org/pypi/pyserial)
3. Open "GBCartRead_v.1.4.2.py" and change the serial port to the serial port that your Arduino is connected on. You can find this out    from the Arduino software by going to Tools -> Serial port when the Arduino is plugged in
4. Run the script.Press 1 to Dump the ROM, 2 to Backup your RAM or 3 to Load your RAM file. Hashes (#) will start printing every few seconds and a file called <gametitle>.gb or .sav will be created if    you chose option 1 or 2. If you choose option 3, it will load the save from <gametitle>.sav.


REVISION HISTORY
-----------------------
v1.4.1 (19 September 2014)
- Added Game Boy Camera compatibility.
- Fixed stout buffer in Python.
- Some changes in the Arduino Sketch.

v1.4 (30 August 2013)
- Added gbcartread.exe program for Windows (with source) which can be used instead of using the Python script and is a bit faster

v1.3.1 (2 May 2011)
- Updated schematic as R19, R20 and R31 were actually acting as voltage dividers

v1.3 (9 April 2011)
- Added RAM writing ability
- Fixed MBC2 reading RAM overflow relating to the first 4 bits not being ignored properly
- Cleaned up bank select code to use BitRead instead of checking each bit ourselves
- Fixed selecting wrong RAM size when reading
- Fixed incorrect check if RAM was present before reading
- Removed unnecessary changing of data pins to inputs after MBC was initialised when reading RAM

v1.2 (2 April 2011)
- Added RAM saving ability.
- Now prints the amount of data read in 64K increments (i.e ###64K###128K###192K)
- Changed <gametitle>.rom to <gametitle>.gb

v1.1 (21 March 2011)
- ROM reading is now fully automated.
- The Game Title, MBC type, ROM size and RAM size are presented in the Python script.

v1.0 (19 March 2011)
- Reading ROM only, user to change the maximum ROM bank to read


----------------------------------------------------------------------------
(c) 2011-2014 by insideGadgets
http://www.insidegadgets.com

This work is licensed under a Creative Commons Attribution-NonCommercial 3.0 Unported License.
http://creativecommons.org/licenses/by-nc/3.0/
