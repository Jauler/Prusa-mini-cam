# Prusa Mini Cam

This is a small camera module for Prusa Mini+ 3D printer based on ESP32-CAM module.
And added temperature and pressure sensor just for fun.

## Quick start

### Step 1

Modify esphome/secrets.yaml to match your WiFi SSID, password, and generate random secure password for your camera setup.

For exmaple, the contents of esphome/secrets.yaml can look like this:
```yaml
substitutions:
  prusa_mini_cam_passwd: "your_very_secure_random_camera_password"
  wifi_ssid: "Your_WiFi_Name"
  wifi_passwd: "You_WiFi_Password"
```

Obviously - change values to match your network

### Step 2

Of this is the first time flashing ESPHome to Your ESP32, you will need to physically connect Your ESP32 to the computer.
One of the simplest ways to do that is with any USB-to-UART converter.

Instructions on how to do that can be found [here](https://esphome.io/guides/physical_device_connection.html)

### Step 3

Flash current configuration to the ESP32-CAM board:
```sh
docker run --rm -v "${PWD}":/config --device=/dev/ttyUSB0 -it esphome/esphome run esphome/prusa_mini_cam.yaml
```

### Step 4


If ESP32-CAM is able to succesfully connect to Your WiFi - a red LED on the board will light up.
That means, that you should be able to see the camera feed at http://<pursa_mini_cam_IP_address>:8080

### Step 5

If you have Home Assistant configuration - you can now add [ESPHome](https://www.home-assistant.io/integrations/esphome/) integration.


