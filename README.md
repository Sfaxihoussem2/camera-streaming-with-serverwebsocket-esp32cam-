# ESP32-CAM Real-Time Video Streaming over WebSocket

**Firmware and client-side components for continuous JPEG video streaming from an ESP32-CAM to a WebSocket server.**

---

## Project Overview

This project enables low-latency video streaming from an ESP32-CAM module. The microcontroller captures frames, encodes them as JPEG, and transmits them continuously to a WebSocket server. A companion server or web client can then display or process the live feed.

It forms a core building block for surveillance, robotics teleoperation, smart glasses, and remote monitoring systems.

---

## Key Features

- Continuous JPEG frame capture from ESP32-CAM
- WebSocket-based transport for real-time delivery
- Configurable resolution and quality (PSRAM-aware)
- Wi-Fi connectivity with automatic reconnection patterns
- Compatible with Node.js, Python or any WebSocket server

---

## Hardware

- ESP32-CAM (AI-Thinker recommended)
- Stable 5V power supply (important for camera stability)
- Optional: external antenna for better range

---

## Software Requirements

- Arduino IDE with ESP32 board package
- Libraries: WiFi, ArduinoWebsockets (or equivalent), ESP32 Camera driver
- A running WebSocket server (Node.js example or custom)

---

## Configuration

Edit the following in the firmware:

```cpp
const char* ssid = "your_ssid";
const char* password = "your_password";
const char* websocket_server_host = "ip_or_domain";
const uint16_t websocket_server_port = 8080; // example
```

Board settings (Arduino IDE):
- Board: ESP32 Wrover Module (or AI-Thinker ESP32-CAM)
- Partition Scheme: Default with SPIFFS / appropriate for camera
- PSRAM: Enabled

---

## How It Works

1. ESP32-CAM connects to Wi-Fi.
2. Initializes the camera sensor.
3. Establishes a WebSocket connection to the server.
4. Continuously captures frames → JPEG encode → send binary frames over WebSocket.

The receiving side can reconstruct and display the stream or forward it to a web dashboard.

---

## Repository Structure

- `CameraWeb/` — related web / camera assets
- `cameraws/` — WebSocket streaming related code
- Firmware sketches for the ESP32-CAM

---

## Common Issues

| Issue                        | Possible Solution                                      |
|-----------------------------|--------------------------------------------------------|
| Camera init fails           | Check wiring, power supply, and correct camera model   |
| Choppy stream               | Lower resolution / JPEG quality, improve Wi-Fi         |
| Connection drops            | Add reconnection logic and watchdog                    |
| Brown-out / resets          | Use better 5V supply and decoupling capacitors         |

---

## Future Improvements

- Add authentication to the WebSocket stream
- Implement adaptive quality based on bandwidth
- Pair with a production-ready Node.js / Python streaming server
- Support multiple concurrent viewers
- Integrate motion detection or on-device inference

---

## Related Projects

- [Smart Glasses for Blind Persons](https://github.com/Sfaxihoussem2/smart-glasses-for-blind-person-) — uses similar ESP32-CAM + Edge AI pipeline
- [Sea Drone](https://github.com/Sfaxihoussem2/Sea-drone-) — live video + telemetry
- Server-side WebSocket projects in this account

---

## Author

**Houssem Eddine Sfaxi**  
Embedded Systems & IoT Engineer  
[GitHub](https://github.com/Sfaxihoussem2) · [Portfolio](https://sfaxihoussem2.github.io/My-portfolio/) · [LinkedIn](https://www.linkedin.com/in/houssem-sfaxi-3272a9280)

---

## License

Educational and portfolio use. Contact for commercial licensing or collaboration.
