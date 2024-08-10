# Fertile and Infertile Egg Classification Project

This project utilizes the ESP32 microcontroller along with an AI-based model to classify fertile and infertile eggs using an attached camera. The project leverages the Edge Impulse inferencing SDK for running the classification model directly on the ESP32.

## Project Components

- **ESP32 Board**: The core microcontroller used in this project, specifically the AI Thinker model, which includes PSRAM for efficient camera processing.
- **Camera Module**: The ESP32 is connected to a camera module, which captures images of the eggs for classification.
- **Edge Impulse Inferencing SDK**: The SDK is used to run the trained machine learning model that classifies the images into fertile or infertile eggs.
- **Wi-Fi Connectivity**: The ESP32 connects to a Wi-Fi network, allowing users to access the classification results via a web interface.

## Hardware Requirements

- ESP32 AI Thinker Board
- Camera module compatible with the ESP32 (AI Thinker model)
- USB Cable for programming and power
- Wi-Fi network for connecting the ESP32

## Software Requirements

- Arduino IDE with ESP32 board support
- Edge Impulse SDK installed and configured
- Wi-Fi credentials for connecting the ESP32 to a local network

## Project Setup

1. **Hardware Setup**:
    - Connect the camera module to the ESP32 according to the pin configuration defined in the code.
    - Ensure that the ESP32 board is connected to your computer via USB.

2. **Software Setup**:
    - Install the necessary libraries in the Arduino IDE:
      - `esp_camera`
      - `WiFi`
      - `ESPAsyncWebServer`
      - `AsyncTCP`
      - `Edge Impulse Inferencing SDK`
    - Configure the Wi-Fi credentials in the code:
      ```cpp
      const char* ssid = "Your_SSID";
      const char* password = "Your_Password";
      ```
    - Load the project code into the Arduino IDE and upload it to the ESP32 board.

3. **Edge Impulse Model**:
    - Train a model using the Edge Impulse platform for classifying fertile and infertile eggs.
    - Deploy the trained model to the ESP32 by exporting the inference code from Edge Impulse and integrating it with the project.

## Running the Project

1. **Power the ESP32**: Once the code is uploaded, power the ESP32 via USB or an external power source.
2. **Connect to Wi-Fi**: The ESP32 will automatically connect to the Wi-Fi network specified in the code. Monitor the Serial output for connection status and IP address.
3. **Access the Web Interface**:
    - Open a web browser and enter the IP address of the ESP32 to access the object detection results.
    - The webpage will dynamically update with the classification results as the ESP32 processes images.

## Code Overview

- **Camera Configuration**: The camera is initialized with specific pins and settings for the AI Thinker model.
- **Wi-Fi Setup**: The ESP32 connects to the specified Wi-Fi network and hosts a web server.
- **Image Capture and Processing**: The camera captures images, which are then processed and passed to the Edge Impulse model for classification.
- **WebSocket Server**: The ESP32 uses WebSocket to update the web interface in real-time with the classification results.

## Troubleshooting

- **Camera Initialization Failed**: Ensure the camera module is correctly connected and the pin configuration matches your setup.
- **Wi-Fi Connection Issues**: Double-check the SSID and password. Verify that the Wi-Fi network is within range.
- **Web Interface Not Loading**: Make sure the ESP32 is connected to the Wi-Fi, and the correct IP address is used.

## Future Enhancements

- Add more categories for classification.
- Implement anomaly detection to identify unclear or invalid images.
- Improve the web interface with more detailed result displays and user controls.

## License

This project is licensed under the MIT License. Feel free to modify and distribute as needed.

---

This README provides an overview of setting up and running the Fertile and Infertile Egg Classification project using ESP32. Follow the instructions carefully to ensure proper functionality and successful classification.
