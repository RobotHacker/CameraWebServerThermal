# CameraWebServerThermal
Yet another version of the classic ESP32-CAM example CameraWebServer, this time with support for the AMG88xx thermal camera module.

# Kinda works
- I'm fairly sure it leaks memory, it crashes after about half a minute when streaming the thermal camera.
- It serves an 8 by 8 image when you go to http://ESP32ipaddress/therm_capture
- It streams 8 by 8 mjpg when you go to  http://ESP32ipaddress:82/therm_stream
- The regular CameraWebServer URLs are unchanged

# To Do
- Fix crash
  - Memory leak?
- Make image/stream larger
  - Stretch pixels?
- Mix in [interpolation code](https://github.com/adafruit/Adafruit_AMG88xx/tree/master/examples/thermal_cam_interpolate)?
- Feed out thermocouple and temperature array via websockets and/or JSON
- Make the color map more adjustable
  - Raise and lower the high and low ends of the color map
  - Replace the color map with custom colors

# The process so far
- Started with [CameraWebServer](https://github.com/espressif/arduino-esp32/tree/master/libraries/ESP32/examples/Camera/CameraWebServer)
- Copied then modified the capture_handler and stream_handler with inspiration from the [Adafruit_AMG88xx thermal_cam example](https://github.com/adafruit/Adafruit_AMG88xx/blob/master/examples/thermal_cam/thermal_cam.ino)

# Hardware
- ESP32-CAM
- AMG8833 breakout module
- USB to serial for programming

# Other inspiration
- https://www.instructables.com/id/M5Stack-IR-Thermal-Camera-Using-AMG8833-Infrared-A/
- https://github.com/hkoffer/M5Stack-Thermal-Camera-
- https://github.com/m600x/M5Stack-Thermal-Camera
- https://learn.sparkfun.com/tutorials/qwiic-grid-eye-infrared-array-amg88xx-hookup-guide/all
- https://github.com/OberBerger/Thermo-camera-ESP32
- https://github.com/smartynov/AMG8833-Thermal-Cam
- https://www.youtube.com/watch?v=tLwYMQjD0l4
  - Color map generation
