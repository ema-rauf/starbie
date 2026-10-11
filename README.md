Starbie

A small motion-controlled desk pet on a custom PCB. A XIAO ESP32-C3 draws a wandering pet on a 0.96" OLED, an MPU6050 reads tilt and shakes, a DHT11 reads temperature and humidity, and two buttons open a radial menu and a stats screen.

Built for Hack Club Half-Life, Week 1 (PCB design). Based on the Week 1 example project by SharKingStudios: https://github.com/SharKingStudios/Starbie

Show Image

Show Image

How it works
Control	What it does
Button 1, first press	Opens the radial menu
Tilt while the menu is open	Moves the selector ball toward NAP, PLAY, FEED or PET
Button 1, second press	Chooses the highlighted action
Button 2	Shows or hides the stats screen (joy, energy, fullness, temperature, humidity)
Shake	Gives the pet a shake reaction
Parts
Part	Reference
Seeed Studio XIAO ESP32-C3	U1
0.96" 128x64 I2C OLED	J1 (4-pin header)
MPU6050 module (GY-521)	J2 (8-pin header)
DHT11 sensor	U2
10k resistor (pull-up on DHT11 data)	R1
Push buttons (Cherry MX footprint)	SW1, SW3

The full list is in bom.csv.

Wiring
XIAO pin	GPIO	Net
D1	3	DHT11_DATA
D2	4	GPIO2 (button 1)
D3	5	GPIO3 (button 2)
D4	6	SCL (OLED and MPU6050)
D5	7	SDA (OLED and MPU6050)

The OLED and the MPU6050 share the same two I2C lines. The ground net is a copper pour on both layers.

Firmware

Starbie/Firmware/Starbie/Starbie.ino is the example sketch from the guide with one change: because this board has SCL on D4 and SDA on D5, the I2C pins are set to I2C_SDA_PIN = 7 and I2C_SCL_PIN = 6.

To build it:

Install Arduino IDE and add the ESP32 board package (esp32 by Espressif Systems).
Install the libraries: Adafruit GFX Library, Adafruit SSD1306, Adafruit MPU6050, DHT sensor library.
Select the board XIAO_ESP32C3 and click Verify/Compile.

The sketch compiles (26% of program storage, 4% of dynamic memory). It has not been uploaded to hardware yet, because the board has not been built.

Repository layout
Starbie/ : KiCad project (.kicad_pro, .kicad_sch, .kicad_pcb)
Starbie/Gerbers/ : Gerber and drill files for manufacturing
Starbie/Firmware/Starbie/ : Arduino sketch
Week 1 Care Package/ : symbol and footprint libraries and 3D models used by the project
bom.csv : parts list
Status

The PCB is designed and routed. The design rules check shows no unconnected items. The only 2 errors are "malformed courtyard" errors on the OLED footprint (J1) that come from the care package footprint.

## Screenshots

![Screenshot From 2026-10-10 06-03-11.png](images/Screenshot%20From%202026-10-10%2006-03-11.png)

![Screenshot From 2026-10-10 06-06-27.png](images/Screenshot%20From%202026-10-10%2006-06-27.png)

![Screenshot From 2026-10-10 06-16-41.png](images/Screenshot%20From%202026-10-10%2006-16-41.png)

![Screenshot From 2026-10-10 06-18-14.png](images/Screenshot%20From%202026-10-10%2006-18-14.png)

![Screenshot From 2026-10-10 06-21-34.png](images/Screenshot%20From%202026-10-10%2006-21-34.png)

![Screenshot From 2026-10-10 06-27-23.png](images/Screenshot%20From%202026-10-10%2006-27-23.png)

![Screenshot From 2026-10-10 06-34-36.png](images/Screenshot%20From%202026-10-10%2006-34-36.png)

![Screenshot From 2026-10-10 07-34-07.png](images/Screenshot%20From%202026-10-10%2007-34-07.png)

![Screenshot From 2026-10-10 18-47-21.png](images/Screenshot%20From%202026-10-10%2018-47-21.png)

![Screenshot From 2026-10-10 18-49-22.png](images/Screenshot%20From%202026-10-10%2018-49-22.png)

![Screenshot From 2026-10-10 18-53-54.png](images/Screenshot%20From%202026-10-10%2018-53-54.png)

![Screenshot From 2026-10-10 18-54-34.png](images/Screenshot%20From%202026-10-10%2018-54-34.png)

![Screenshot From 2026-10-10 18-56-07.png](images/Screenshot%20From%202026-10-10%2018-56-07.png)

![Screenshot From 2026-10-10 18-56-39.png](images/Screenshot%20From%202026-10-10%2018-56-39.png)

![Screenshot From 2026-10-10 18-57-17.png](images/Screenshot%20From%202026-10-10%2018-57-17.png)

![Screenshot From 2026-10-10 18-59-47.png](images/Screenshot%20From%202026-10-10%2018-59-47.png)

![Screenshot From 2026-10-10 19-02-47.png](images/Screenshot%20From%202026-10-10%2019-02-47.png)

![Screenshot From 2026-10-10 19-21-29.png](images/Screenshot%20From%202026-10-10%2019-21-29.png)

![Screenshot From 2026-10-11 08-46-50.png](images/Screenshot%20From%202026-10-11%2008-46-50.png)

![Screenshot From 2026-10-11 09-00-31.png](images/Screenshot%20From%202026-10-11%2009-00-31.png)

![Screenshot From 2026-10-11 09-02-00.png](images/Screenshot%20From%202026-10-11%2009-02-00.png)

![Screenshot From 2026-10-11 09-04-14.png](images/Screenshot%20From%202026-10-11%2009-04-14.png)

![Screenshot From 2026-10-11 09-06-23.png](images/Screenshot%20From%202026-10-11%2009-06-23.png)

![Screenshot From 2026-10-11 09-07-35.png](images/Screenshot%20From%202026-10-11%2009-07-35.png)

