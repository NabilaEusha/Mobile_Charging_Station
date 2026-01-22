# Mobile_Charging_Station
Developed an ESP32-based coin-operated multi-port mobile charging system with real-time control, relay-based power management, LCD interface and RFID authentication for secure, time-bound public charging.

## Overview

This project implements a smart charging station designed for deployment in public environments such as universities, transportation hubs and commercial areas. The system features dual authentication mechanisms (coin-based and RFID) and supports multiple simultaneous charging sessions with independent port control.

## Key Features

- **Dual Authentication System**
  - Coin-operated charging for public access (Ports 2, 3, 4)
  - RFID-based secure authentication for authorized users (Port 1)
  
- **Multi-Port Support**
  - 4 independent charging ports with relay-based control
  - Simultaneous charging capability for multiple users
  
- **Real-Time Monitoring**
  - LCD display showing system status and remaining time
  - Port selection through dedicated push buttons
  
- **Time-Bound Charging**
  - Automatic power cutoff after allocated time
  
- **Safety Features**
  - Electrical isolation between ports using relay modules
  - Debounced input handling to prevent false triggers
  - Automatic timeout for coin validity

## Hardware Components

- ESP32 DevKit C  
- CH616 Multi-Coin Acceptor  
- MFRC522 RFID Module  
- 4-Channel Relay Module  
- 20×4 I2C LCD Display  
- USB Charging Modules (×4)  
- Push Buttons (×4)

## Pin Configuration

### ESP32 Pin Assignments
```
Relay Pins:    25, 26, 27, 14 (Ports 1-4)
Button Pins:   32, 33, 34, 35 (Port selection 1-4)
Coin Acceptor: GPIO 12
RFID SS:       GPIO 5
RFID RST:      GPIO 4
LCD (I2C):     SDA-21, SCL-22
```

## Software Architecture

### Libraries Required
- `Wire.h` - I2C communication
- `LiquidCrystal_I2C.h` - LCD control
- `SPI.h` - SPI communication for RFID
- `MFRC522.h` - RFID reader interface


### Prerequisites
```bash
- Arduino IDE (1.8.x or higher)
- ESP32 Board Support Package
- Required libraries (listed above)
```

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/NabilaEusha/Mobile_Charging_Station
   cd Mobile_Charging_Station
   ```

2. **Install dependencies**
   - Open Arduino IDE
   - Install ESP32 board support via Board Manager
   - Install required libraries via Library Manager

3. **Hardware setup**
   - Connect components according to pin configuration
   - Ensure proper power supply (12V for coin acceptor, 5V for ESP32)

4. **Upload code**
   - Open `esp32/multiportcharge.ino`
   - Select ESP32 Dev Module as board
   - Upload to your ESP32

## Simulation
- Basic functionality can be tested using **Wokwi** before hardware deployment.

## Usage
- **Coin-Based Charging:**  
  Insert a coin → Press Button 2 / 3 / 4 → Charging starts

- **RFID-Based Charging:**  
  Tap RFID card → Press Button 1 → Charging starts (20 seconds)


## Known Limitations

- Coin acceptor may generate false pulses due to mechanical vibrations
- Fixed charging current (no adaptive charging)
- No network-based payment integration (mobile wallets, etc.)
- Breadboard prototype not suitable for harsh environments

## Future Enhancements

- [ ] Mobile payment integration (bKash, Nagad, etc.)
- [ ] Dynamic charging and fast charging current adaptation
- [ ] Cloud-based usage analytics
- [ ] PCB design for robust deployment
- [ ] Weatherproof enclosure design
- [ ] Solar power option for outdoor installations
- [ ] User authentication database
- [ ] Remote monitoring and control

## 👥 Team Members

This project was developed as part of the **ETE 320: Microprocessor and Microcontroller Sessional** course at  
**Chittagong University of Engineering & Technology (CUET)**.

- **Wahida Zannat** — [@WahidaZannat](https://github.com/WahidaZannat)  
- **Puspita Barua** — [@PuspitaBarua](https://github.com/PuspitaBarua)  
- **Nisat Sayara** — [@NisatSayara](https://github.com/nisatsayara)  
- **Maowa Alam Khan** — [@MaowaAlamKhan](https://github.com/Maowakhan)  
- **Nabila Sultana** — [@NabilaSultana](https://github.com/NabilaSultana)


## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
