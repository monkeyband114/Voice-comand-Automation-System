# Voice-comand-Automation-System

This project uses an ESP32 dev board along with an INMP441 microphone to create a voice command system for controlling relays and attached loads.

## Components
- ESP32 dev board
  - Used for running the main logic and WiFi connectivity
- INMP441 microphone
  - Connected to the I2S interface to capture audio
- 4-channel relay 
  - For switching attached loads on/off
- Various loads
  - e.g. lights, fans, etc connected to the relays
  
## Software Features
- WiFi connectivity for HTTP requests
- I2S driver for microphone audio capture
- ESP-NOW support for wireless commands 
- Wit.ai integration over HTTP for speech recognition
- Controls attached loads via relays based on recognized speech commands
- Provides visual feedback via LEDs and LCD display

The code handles microphone setup and audio capture, sending audio to Wit.ai for processing, parsing the response to identify commands, and toggling relays based on the command. Visual feedback is shown during processing and when toggling loads on the LCD display and LED meter.

ESP-NOW functionality allows wireless sending of commands between ESP32 boards, with callback processing to handle received packets.

Overall this allows voice control of attached devices by speaking command phrases like "turn on kitchen" which are recognized by Wit.ai and used to control the appropriate relay/load.

## License
This project is licensed under the MIT License. See the `LICENSE.md` file for details.
Here are some details on setting up this voice command project on your own computer:

## Hardware Setup 
- Get an ESP32 dev board and INMP441 microphone module
- Wire up the I2S pins between the ESP32 and microphone
- Optionally add an I2C LCD display and LED meter
- Connect 4-channel relay module to designated GPIO pins
- Connect lights, fans, etc to each relay channel

## Software Setup
- Install Arduino IDE and ESP32 board support 
- Install Wit.ai library using Arduino Library Manager
- Create a Wit.ai account and app to get an API key
- Edit `define.h` file to specify WiFi and Wit.ai credentials 
- Edit macros to enable any connected devices over relay control or ESP-NOW  
- Upload sketch to ESP32

## Configuration
- The amplify factor can be adjusted to tune the microphone input volume detection
- Sensitivity levels and thresholds may need to be tweaked for your environment
- Additional speech commands can be added by expanding the command processing logic

## Running
- Open the Arduino IDE serial monitor after uploading code
- The device will connect to WiFi and Wit.ai so should show status 
- Speak a voice command phrase to toggle one of the relay channels
- The visual display will provide feedback during processing
- Check serial output to see detection results

With some tweaking to sensitivity levels, this project provides an easy way to start experimenting with ESP32 voice control and home automation applications. Additional devices could be controlled by expanding the command processing logic.
