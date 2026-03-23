# BME690 Sensor Module

## Overview

The **BME690 Sensor Module** is an environmental sensing board designed for accurate measurement of atmospheric parameters. It communicates via the **I2C protocol** and supports both **3.3V and 5V operation**, making it suitable for a wide range of embedded and IoT applications.

---

## Features

* Supports **I2C communication**
* Configurable **I2C address selection**
* Operates on **3.3V and 5V supply**
* Onboard **voltage regulation (5V → 3.3V)**
* Integrated **level shifting for I2C lines**
* Built-in **ESD protection**

---

## Hardware Details

### 1. Power Supply

* The module can be powered using:

  * **3.3V (direct)**
  * **5V input**
* **AP2112K-3.3** LDO regulator is used to convert 5V to 3.3V for the sensor.

---

### 2. I2C Communication

* Communication interface: **I2C**
* Compatible with most microcontrollers (ESP32, STM32, Arduino, etc.)

---

### 3. I2C Address Configuration

The module provides flexible address selection using resistors:

| Resistor Configuration | I2C Address |
| ---------------------- | ----------- |
| R6 = 4.7KΩ             | `0x77`      |
| R7 = 0Ω (0E)           | `0x76`      |

> Note: Populate only one resistor at a time for correct address selection.

---

### 4. Level Shifting

* **BSS138 MOSFETs** are used for bidirectional level shifting
* Ensures safe communication between:

  * 5V logic systems
  * 3.3V sensor

---

### 5. ESD Protection

* **TPD2E2U06DRLR** is used to protect I2C lines from electrostatic discharge (ESD)

---

## Pin Configuration

| Pin Name | Description     |
| -------- | --------------- |
| VCC      | 3.3V / 5V Input |
| GND      | Ground          |
| SDA      | I2C Data Line   |
| SCL      | I2C Clock Line  |

---

## Typical Connection Diagram

```
MCU            BME690 Module
----           --------------
VCC   -------> VCC
GND   -------> GND
SDA   -------> SDA
SCL   -------> SCL
```

---

## Applications

* Environmental monitoring
* Smart home systems
* Industrial IoT
* Weather stations
* Air quality monitoring

---

## Notes

* Ensure correct **I2C address selection** before powering the module
* Do not populate both R6 and R7 simultaneously
* Use proper pull-up resistors if required (typically already present on board)

---

## License

This project is open-source. Feel free to use and modify as per your requirements.

---

## Author

Developed for embedded and IoT applications.

---
