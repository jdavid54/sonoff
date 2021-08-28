# sonoff

# how to flash
	https://www.instructables.com/How-to-Get-Started-With-ESP8285-Module-/
	https://tropratik.fr/programmer-esp8285-avec-arduino
	https://github.com/arendst/Tasmota/issues/3698
	bestlink : https://www.tutos.eu/6215 

# adaptor for 8285
	https://notenoughtech.com/home-automation/esp8266-flash-adapter/

# Pour télécharger le firmware Tasmota 
	
[Tasmota releases](https://github.com/arendst/Tasmota/releases)

* 1 - [logiciel de flash NodeCMU PyFlasher](https://github.com/marcelstoer/nodemcu-pyflasher/releases/tag/v4.0) / [tuto youtube](https://youtu.be/3aLcRPbp1As)

* 2 - [Tasmotizer](https://notenoughtech.com/home-automation/tasmotizer/)

# esp8285 datasheet
	https://www.espressif.com/en/products/socs
	https://www.espressif.com/sites/default/files/documentation/0a-esp8285_datasheet_en.pdf

# install board for Arduino IDE
	https://randomnerdtutorials.com/how-to-install-esp8266-board-arduino-ide/

# json file
	http://arduino.esp8266.com/stable/package_esp8266com_index.json

# Connection FTDI - Sonoff

## FTDI to ESP8285 board connection.

### Kindly Note(Important): ESP8255 accepts max 3.3 v NOT 5v.

| FTDI Pin | ESP8285 Pin | 
|----------|:-------------:|
|3.3v |      VCC|
|Gnd  |      GND|
|Rx    |     Tx|
|Tx    |     Rx|

# Flash mode/uploading code: 

* 1 - put Sonoff into flash mode
Then ESP8285 IO0 and ESP8285 Gnd have to be connected to each other else don't connect(like post code upload). Refer images attached using a on/off switch to on and off flash and operational mode. Once use case is finalized one can de-solder this switch. GPIO 0 i.e IO0 and Gnd of ESP8285 has to be shorted/connected before FTDI is in powered up. This tells the board to in flash mode or upload code to chip.

* 2- Select Tools -> Board -> Generic 8285 Board
Upload any ESP8266 compatable code.  (Tasmota, etc.)
Once you see "Upload Complete" status in Arduino IDE means success and you can proceed to next step. Else make sure connection are made as per above steps.


* 3 - Disconnect GPIO 0 and Gnd.
Now re power board(I use 2 x 1.5v AA regular battery) connect LED or any output to pin the code uploaded needs. If you don't have any LED GPIO2 points to onboard blue led. You can upload blink.ino and make sure to trigger pin 2.

* 4 - Test Run
Now the default on board blue color tiny led should start blinking at an set interval of 1 sec gap.
