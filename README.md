# starbie-pcb
My Starbie

A tiny star-shaped desk pet. A XIAO ESP32-C3 draws a wandering pet on a 0.96" OLED screen. You can open a radial menu with a button, tilt the board to pick an action, and check the room temperature and humidity on a stats screen.

I made this for Half Life Week 1, following the Starbie guide


Hardware
Microcontroller: Seeed Studio XIAO ESP32-C3
Display: 0.96" 128x64 I2C OLED (4-pin header)
Motion sensor: MPU6050 module (8-pin header, shares the I2C lines with the OLED)
Environment sensor: DHT11, with a 10k pull-up resistor on the data line
Controls: 2 push buttons (Cherry MX style footprints)
Board: custom star-shaped PCB designed in KiCad

Pin connections
Part	XIAO pin	ESP32-C3 GPIO
OLED SDA and MPU6050 SDA	D4	GPIO6
OLED SCL and MPU6050 SCL	D5	GPIO7
DHT11 data	D1	GPIO3
Button 1	D2	GPIO4
Button 2	D3	GPIO5
Controls
Control	What it does
Button 1, first press	Opens the radial menu
Tilt while the menu is open	Moves the selector ball
Button 1, second press	Chooses the highlighted action
Button 2	Shows or hides the stats screen
Shake the board	Gives the pet a shake reaction

Hardware/: KiCad project (schematic, PCB and the footprint and symbol libraries I used)
Gerbers/: manufacturing files for the PCB
Firmware/Starbie/: Arduino sketch
Images/: screenshots of the design

Firmware

The code is an Arduino sketch based on the starter code from the Half Life Week 1 guide.

To upload it:

Install the Arduino IDE.
Add the ESP32 board package URL in File > Preferences: https://espressif.github.io/arduino-esp32/package_esp32_index.json
In Boards Manager, install esp32 by Espressif Systems, then select the board XIAO_ESP32C3.
Install the libraries: Adafruit GFX Library, Adafruit SSD1306, Adafruit MPU6050 and DHT sensor library.
Open Firmware/Starbie/Starbie.ino and upload.

What I learned
Ive learned how to use KiCAD and how to make custon PCB boards for my future projects.

What I'd improve
Make more custom changes to it but ill do it soon.
