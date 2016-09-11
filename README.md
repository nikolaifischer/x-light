# x-light

Bluetooth Commands for the x-light Smart Bulb from the chinese company we-smart. The commands are send using the bluez suite for linux.
These Codes can be used to control the bulb from your PC or from any other app which supports bluetooth.
The lightbulb can than consequently be integrated into Smart Hubs like the [home-assistant.io](http://www.home-assistant.io/)

The color codes presented here are far from complete. If you find out more codes, feel free to open a Pull Request and I will add them.




## 1. Install Bluez
[http://www.bluez.org/](http://www.bluez.org/)

## 2. Make sure your BT Interface is up:
	sudo hciconfig hci0 up
    
## 3. Find the MAC Adress of your Bulb
	sudo hcitool lescan

There should be an device named "x-light@WE-SMART". Note the MAC-Adress


### 4. Write to the bulb to make it change it's color:

	gatttool -b {your-MAC} --char-write -a 0x0012 -n  {color-code}
    
Insert the the correct Mac-Adress for the {your-MAC} field and the color you want for the {color-code} field.
Use this repository to find correct color codes.
