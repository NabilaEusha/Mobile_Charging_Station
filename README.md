# Mobile Charging Station

A smart charging station for public environments like universities, transportation hubs and commercial areas. Features dual authentication (coin + RFID) with multi-port simultaneous charging capability.

## Key Features

- **Dual Authentication**: Coin-operated (Ports 2-4) and RFID access (Port 1)
- **Multi-Port Support**: 4 independent relay-controlled charging ports
- **Real-Time Display**: LCD showing system status and remaining time
- **Auto Cutoff**: Time-bound charging with automatic power termination
- **Safety**: Debounced inputs, electrical isolation, coin timeout protection

## Hardware Components

- ESP32 DevKit C  
- CH616 Multi-Coin Acceptor  
- MFRC522 RFID Module  
- 4-Channel Relay Module  
- 20×4 I2C LCD Display  
- USB Charging Modules (×4)  
- Push Buttons (×4)

## Pin Configuration

```
Relay Pins:    25, 26, 27, 14 (Ports 1-4)
Button Pins:   32, 33, 34, 35 (Port selection 1-4)
Coin Acceptor: GPIO 12
RFID SS:       GPIO 5
RFID RST:      GPIO 4
LCD (I2C):     SDA-21, SCL-22
```

## Libraries Required

- `Wire.h` - I2C communication
- `LiquidCrystal_I2C.h` - LCD control

## Installation

**Prerequisites:**
- Arduino IDE (1.8.x or higher)
- ESP32 Board Support Package

**Steps:**

1. Clone the repository
   ```bash
   git clone https://github.com/NabilaEusha/Mobile_Charging_Station
   cd Mobile_Charging_Station
   ```

2. Install dependencies
   - Open Arduino IDE
   - Install ESP32 board support via Board Manager
   - Install required libraries via Library Manager

3. Hardware setup
   - Connect components per pin configuration
   - Power: 12V for coin acceptor, 5V for ESP32

4. Upload code
   - Open `esp32/multiportcharge.ino`
   - Select ESP32 Dev Module
   - Upload to board

## Simulation

Basic functionality can be tested using **Wokwi** before hardware deployment.

## Usage

**Coin-Based Charging:**  
Insert coin → Press Button 2/3/4 → Charging starts

**RFID-Based Charging:**  
Tap RFID card → Press Button 1 → Charging starts (20 seconds)

## Limitations

- Coin acceptor may generate false pulses from mechanical vibrations
- Fixed charging current (no adaptive/fast charging)
- No mobile payment integration
- Breadboard prototype unsuitable for harsh environments

## Future Enhancements

- Mobile payment (bKash, Nagad)
- Dynamic/fast charging support
- Cloud analytics
- PCB design for deployment
- Weatherproof enclosure
- Solar power option
- User authentication database
- Remote monitoring

## Team

Developed for **ETE 320: Microprocessor and Microcontroller Sessional** at **Chittagong University of Engineering & Technology (CUET)**

- **Wahida Zannat** — [@WahidaZannat]()  
- **Puspita Barua** — [@PuspitaBarua](https://github.com/PuspitaBarua)  
- **Nisat Sayara** — [@NisatSayara](https://github.com/nisatsayara)  
- **Maowa Alam Khan** — [@MaowaAlamKhan](https://github.com/Maowakhan)  
- **Nabila Sultana** — [@NabilaSultana](https://github.com/NabilaEusha)

## Contributing

Contributions welcome! Feel free to submit a Pull Request.

