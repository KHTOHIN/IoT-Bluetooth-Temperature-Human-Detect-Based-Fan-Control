# IoT — Bluetooth, Temperature & Human-Detection Based Fan Control

An Arduino project that controls a fan automatically based on **room temperature** and **human presence**, with manual override over **Bluetooth**. Built as a university IoT course project.

## How It Works

1. **Bluetooth override** — send `0` from a Bluetooth terminal app to turn the fan off; any other character turns it on at full speed.
2. **Human detection** — a PIR sensor checks whether someone is in the room. If the room is empty, the fan turns off and the LCD shows *Empty Room*.
3. **Temperature-based speed** — when someone is present, the temperature sensor sets the fan speed with PWM:

| Temperature | Fan speed |
|---|---|
| below 20 °C | Off |
| 20–23 °C | 30% |
| 23–26 °C | 60% |
| 26–30 °C | 80% |
| 30 °C and above | 100% |

The current status is shown on a 16×2 LCD.

## Hardware

- Arduino Uno (or compatible)
- LM35 temperature sensor → `A1`
- PIR motion sensor → pin `7`
- HC-05 / HC-06 Bluetooth module → serial (9600 baud)
- 16×2 LCD → pins `12, 11, 5, 4, 3, 2`
- DC fan with transistor driver → PWM pin `9`

## Getting Started

1. Open the `.ino` file in the Arduino IDE
2. Wire the components as listed above
3. Upload the sketch to the board
4. Pair your phone with the Bluetooth module and use any Bluetooth serial terminal app

## Tech

C++ (Arduino) · LiquidCrystal library

## Author

**Kawsar Hamid** · [Portfolio](https://kawsarhamid.vercel.app) · [LinkedIn](https://www.linkedin.com/in/kawsar-hamid-tohin/)
