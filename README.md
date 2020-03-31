# Arduino-Code
Arduino OCF example code

# Install Arduino-Code
curl https://openconnectivity.github.io/Arduino-Code/arduino/install.sh | bash

# instructions to get started (on Linux)
- Install Arduino IDE
  - instructions: https://www.arduino.cc/en/Guide/Linux
  - get the archive from arduino.cc
  - move the directory to ~/arduino-home
  - cp -rf ~/Downloads/arduino-1.8.10-linux64/arduino-1.8.10 arduino-home
  - cd ~/arduino-home
  - sudo ./install.sh
- Install iotivity-lite version for Arduino
  - cd ~
  - curl https://openconnectivity.github.io/IOTivity-Lite-setup/install.sh | bash
  - cd iot-lite
  - (optional?) Try Arduino to make sure it works
- open the Arduino IDE
  - Load board support for the target board
  - Load all necessary libraries
- Make sure the board is selected and a valid port is selected
- Try the blink application
- Edit the source file
  - gedit ~/iotivity-lite/apps/server_arduino.cpp &
  - change: oc_set_mtu_size(1024); //on line 134
  - change: oc_set_max_app_data_size(2048); //on line 135
  - change the serial rate: Serial.begin(115200); //on line 181
  - save the changes
- Run arduino build script
  - Be sure the Arduino IDE isn’t running, or the upload won’t work
    file to compile will be server_arduino.cpp
  - cd ~/iotivity-lite/port/arduino
  - ./build_arduino.sh --arch sam --secure —upload
