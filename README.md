DHT11 Demo (Arduino Uno / UNO R4)

Brief demo project that reads humidity and temperature from a DHT11 sensor and prints the values over Serial. See `src/main.cpp` for the implementation.

Using CLion

- Open the project in CLion.
- Recommended to use the Arduino or PlatformIO plugin for flashing and serial monitor support.
- Build/run configuration depends on your board/toolchain (Arduino CLI, PlatformIO, or custom CMake).
- This repository includes a `platformio.ini` which makes building/flashing with PlatformIO straightforward.

IDE Version

Tested with CLion 2025.3.2.

Code Overview

- Entry: `src/main.cpp`.
- Behavior:
  - Initializes `Serial` at 9600 baud.
  - Initializes the DHT11 sensor on digital pin defined by `DHTPIN` (defaults to pin 2).
  - Reads humidity and temperature (Celsius) using the DHT library.
  - Checks for failed reads (NaN) and prints an error message if the read failed.
  - On success, prints a one-line report: humidity and temperature every 2 seconds.
- Key calls: `dht.begin();` then `dht.readHumidity();` and `dht.readTemperature();`.

Libraries

- DHT (Adafruit DHT sensor library or compatible `DHT.h`).
- `Arduino.h` (core)

Install via Arduino Library Manager or PlatformIO library registry.

Dependencies

- Arduino core for your board (e.g., Arduino AVR, Arduino Uno R4 core, ESP32, ESP8266, etc.).
- DHT sensor library listed above.
- I2C is not required for this project (DHT11 uses a single-wire digital interface).

Components used with the DHT11

- DHT11 temperature & humidity sensor module (or bare DHT11 sensor).
- Microcontroller board (Arduino Uno / UNO R4, Nano, Mega, ESP32, etc.).
- Pull-up resistor for the data line (4.7k–10k recommended) — many breakout modules include this already.
- Jumper wires and breadboard.

Wiring (typical)

- DHT VCC -> 5V (or 3.3V if your module requires it; match MCU voltage).
- DHT GND -> GND.
- DHT DATA -> digital pin 2 (matches `#define DHTPIN 2` in `src/main.cpp`).
- Add a 4.7k–10k pull-up resistor between DATA and VCC if your module does not include one.

Software Requirements

- CLion 2025.3.2
- Arduino toolchain (Arduino IDE or Arduino CLI), or
- PlatformIO (recommended for integrated build/flash in CLion)
- Board support package / core for your target board (install via Arduino Boards Manager or PlatformIO)

Hardware Requirements

- MCU board compatible with your chosen voltage (3.3V or 5V) — match the DHT11 module.
- DHT11 sensor or DHT11 breakout module.
- USB cable for programming and power.
- Optional: logic level shifter if MCU voltage differs from the DHT module and level shifting is required.

Author

Ayush1Sikarwar (GitHub)
