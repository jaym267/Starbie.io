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

| Part | What it's for | Qty | Unit Price | Total | Vendor |
|---|---|---|---|---|---|
| Seeed XIAO ESP32C3 (SKU 113991054) | The brain; runs the Starbie code | 1 | $4.99 | $4.99 | [Seeed (via Hackster)](https://hackster.io/products/buy/116992) |
| 0.96" SSD1306 OLED | The screen Starbie lives on | 1 | $5.09 | $5.09 | [52Pi](https://52pi.com/products/52pi-oled-display-module-i2c-iic-128x64-pixel-0-96-inch-display-module-yellow-blue-two-color-display-compatible-with-raspberry-pi-arduino-51-series-mcu-stm32-r3-and-mega) |
| GY-521 MPU6050 | Detects tilt and shake | 1 | $6.99 | $6.99 | [Hackster Store](https://hackster.io/products/buy/379) |
| DHT11 (4-pin) | Measures temperature and humidity | 1 | $2.00 | $2.00 | [Digi-Key](https://www.digikey.com/en/products/detail/universal-solder-electronics-ltd/DHT11/16822119) |
| Cherry MX1A-E1NN switch | The two buttons | 2 | $1.25 | $2.50 | [Digi-Key](https://azcus.digikey.com/en/products/detail/cherry-americas-llc/MX1A-E1NN/40084) |
| 10k resistor (CF14JT10K0) | Pull-up for the DHT11 data line | 1 | $0.10 | $0.10 | [Digi-Key](https://www.digikey.com/en/products/detail/stackpole-electronics-inc/CF14JT10K0/1830374) |
| PCB (5 boards) | The star board itself | 1 | $2.00 | $2.00 | [JLCPCB](https://jlcpcb.com) |
|Adafruit Dark Gray DSA Keycaps (10 pack) | Caps for the two MX switches | 1 | 5.95 | 5.95 | [[Buy](KEYCAP_LINK)](https://adafruit.com/product/5012) |
| Tax & shipping | Whole order | — | — | $0.00 | — |

**Funded total: $29.44** (keycaps not included)
