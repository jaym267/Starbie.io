STARBIE
<img width="732" height="642" alt="Screenshot 2026-10-11 195856" src="https://github.com/user-attachments/assets/b6da547d-b48e-4d0e-8060-a61781cf3535" />
<
<img width="559" height="420" alt="Screenshot 2026-10-11 164305" src="https://github.com/user-attachments/assets/ba7d2dc8-f870-435e-bd62-d105a7aceec5" />

 a tiny motion control digital pet that lives on a star-shaped PCB 
 ##Hardware 
- **Seeed XIAO ESP32-C3**: the microcontroller that runs everything
- **0.96" SSD1306 OLED (128x64)**: the screen Starbie lives on
- **MPU6050**: accelerometer/gyro for tilt and shake controls
- **DHT11**: temperature and humidity sensor
- **2 Cherry MX switches**: buttons for the menu and stats screen
- **10k resistor**: pull-up for the DHT11

The OLED and MPU6050 share the same I2C lines. The DHT11 is on D1, and the buttons are on D2 and D3.

## How it works
| Control | What it does |
|---|---|
| Button 1 | Opens the radial menu / picks the highlighted option |
| Tilt (menu open) | Moves the selector |
| Button 2 | Shows or hides the stats screen |
| Shake | Starbie does a shake reaction |
Menu options: **NAP**, **PLAY**, **FEED**, and **PET**, each with its own animation.

## What I did
- Designed the schematic and PCB in **KiCad 10**, including the star-shaped board outline
- Routed the board using both copper layers with a ground pour, and passed DRC
- Exported Gerbers for manufacturing
- Set up the firmware in **Arduino IDE** with the ESP32 board package and the required libraries
- Added a custom **sparkle trail** effect that blinks behind Starbie as it walks

## Files
- `MyStarbie/`: KiCad project, schematic, PCB, and Gerbers (`production/Starbie Gerbers.zip`)
- `Starbie.ino`: firmware with my sparkle edit

## Bill of Materials (BOM)

| Ref | Part | Qty | Notes |
|---|---|---|---|
| U1 | Seeed XIAO ESP32-C3 | 1 | Microcontroller, surface-mounted (unsoldered version) |
| J1 | 0.96" SSD1306 OLED, 128x64, I2C | 1 | 4-pin: GND, VCC, SCL, SDA |
| J2 | GY-521 MPU6050 | 1 | Accelerometer/gyro, 8-pin |
| U2 | DHT11 | 1 | Temperature/humidity sensor, bare 4-pin |
| R1 | 10k ohm resistor, 1/4W | 1 | Pull-up for DHT11 data |
| SW1, SW2 | MX-style switches | 2 | 5-pin PCB mount |
| — | MX keycaps | 2 | For the two switches |
| — | Starbie PCB | 1 | Star-shaped, 2-layer, made from my Gerbers |
