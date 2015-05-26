# ESP_SSD1306
SSD1306 display library for the ESP8266 board (modified from Adafruit_SSD1306)

This ESP_SSD1306 library is a copy of the Adafruit_SSD1306 library with some modifications in order to work with the ESP8266 board.

This library is intended to be used with the Arduino IDE from https://github.com/esp8266/arduino which supports ESP8266 boards.

Place the ESP_SSD1306 library folder to your /libraries/ folder. You may need to create the libraries subfolder if its your first library. Restart the IDE.

This library works in conjunction with the default's Adafruit_GFX library, but it's needed to do a little modification: for the Adafruit_GFX library to work with the ESP8266, please be sure to insert the line "#elif defined ESP8266" in the Adafruit_GFX.cpp file.
Otherwise comment the line   //#define pgm_read_byte(addr)...

Code in Adafruit_GFX.cpp should look like this:

	#ifdef __AVR__
	 #include <avr/pgmspace.h>
	#elif defined ESP8266    //Added for compatibility with ESP8266 BOARD
	#else
	 #define pgm_read_byte(addr) (*(const unsigned char *)(addr))
	#endif


Follows original README.txt from Adafruit
-----------------------------------------

This is a library for our Monochrome OLEDs based on SSD1306 drivers

  Pick one up today in the adafruit shop!
  ------> http://www.adafruit.com/category/63_98

These displays use SPI to communicate, 4 or 5 pins are required to  
interface

Adafruit invests time and resources providing this open source code, 
please support Adafruit and open-source hardware by purchasing 
products from Adafruit!

Written by Limor Fried/Ladyada  for Adafruit Industries.  
Scrolling code contributed by Michael Gregg
BSD license, check license.txt for more information
All text above must be included in any redistribution

To download. click the DOWNLOADS button in the top right corner, rename the uncompressed folder Adafruit_SSD1306. Check that the Adafruit_SSD1306 folder contains Adafruit_SSD1306.cpp and Adafruit_SSD1306.h

Place the Adafruit_SSD1306 library folder your <arduinosketchfolder>/libraries/ folder. You may need to create the libraries subfolder if its your first library. Restart the IDE.

You will also have to download the Adafruit GFX Graphics core which does all the circles, text, rectangles, etc. You can get it from
https://github.com/adafruit/Adafruit-GFX-Library
and download/install that library as well 
