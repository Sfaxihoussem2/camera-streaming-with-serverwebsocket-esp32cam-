# Camera Streaming with Server WebSocket (ESP32-CAM)

## Description
This project allows capturing and continuously streaming video from an ESP32-CAM camera via a WebSocket server. The microcontroller connects to a Wi-Fi network and sends the captured images to the specified WebSocket server.

## Required Hardware
- ESP32-CAM (AI-Thinker model)
- 5V power supply for ESP32-CAM
- WebSocket server (can be local or remote)
- Wi-Fi connection

## Features
- Captures images in JPEG format using the ESP32-CAM.
- Connects to a Wi-Fi network.
- Transmits captured images to a WebSocket server.
- Supports different image resolutions depending on the presence of PSRAM.

## Installation and Configuration
1. **Code Configuration**
   - Modify the Wi-Fi credentials in the code:
     ```cpp
     const char* ssid = "your_ssid";
     const char* password = "your_password";
     ```
   - Configure the WebSocket server address and port:
     ```cpp
     const char* websocket_server_host = "ip_address_or_domain";
     const uint16_t websocket_server_port = port;
     ```

2. **Upload the Code to the ESP32-CAM**
   - Use the Arduino IDE with the necessary libraries (WiFi, ArduinoWebsockets, ESP32 Camera).
   - Select "ESP32 Wrover Module" as the board and ensure "PSRAM" is enabled.

3. **Start a WebSocket Server**
   - You can use a WebSocket server based on Node.js, Python, or any other compatible environment.
   - Ensure the server is listening on the same port defined in the code.

4. **Run the Project**
   - Power up the ESP32-CAM and open the serial monitor to see the assigned IP address.
   - Ensure the WebSocket server is running.
   - The ESP32-CAM will continuously send captured images to the WebSocket server.

## Common Issues and Solutions
- **Wi-Fi Connection Issue**: Check that the credentials are correct and the network is accessible.
- **Camera Initialization Error**: Ensure the correct camera model is selected and the wiring is correct.
- **Choppy or Slow Video Stream**: Try adjusting the JPEG quality or image size in the code settings.

## Future Improvements
- Adding a web interface to view the live stream.
- Optimizing frame rate and image quality.
- Integrating with a cloud server for image storage and analysis.

---



with open("README.md", "w", encoding="utf-8") as file:
    file.write(readme_content)

print("README.md created successfully!")
