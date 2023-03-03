# MatrixClock_MicropythonESP
A simple clock for a 64x32 HUB75 LED matrix display with scheduled NTP sync and Sensirion SHT40 ambient sensor.

# Setup

## RGB LED matrix 64x32
The display (23,95€) is from WaveShare (and was much cheaper than the similar product from Adafruit):
- https://www.waveshare.com/wiki/RGB-Matrix-P4-64x32
- https://eckstein-shop.de/WaveShare-RGB-Full-Color-LED-Matrix-Panel-64x32-Pixels-4mm-Pitch-Adjustable-Brightness

Here I've found very valuable information about how to use this kind of display:
- https://www.bigmessowires.com/2018/05/24/64-x-32-led-matrix-programming/
- https://www.sparkfun.com/news/2650

## Power supply
Interestingly enough, the display can be used without power supply, i.e. the small current fed into the HUB75 connector is enough to have the red pixels light up dimly, which is perfect for my use case as a night clock. During daytime, I'll turn on the 5V DC supply using a relay (yet to be implemented). The color of the display is yellow, which is a combination of red and green.

The 5V power supply is converted from a 12V power supply using this handy little DC-DC step-down converter (3.50€) with 10W output (15W max):
- https://eckstein-shop.de/LM2596SDC-DCeinstellbarerStep-DownSpannungsreglermitLED-VoltmeterAdjustablePowerModul

## I²C temperature and pressure sensor
The sensor (7.95€) came on a convenient break-out board from Adafruit:
- https://learn.adafruit.com/adafruit-sht40-temperature-humidity-sensor
- https://eckstein-shop.de/AdafruitSensirionSHT40Temperature26HumiditySensor-STEMMAQT2FQwiic

# Dependencies

This project requires [Ben Emmett's Hub75MicroPython](https://github.com/benjohnemmett/Hub75MicroPython) library, which is perfectly suitable for a simple MicroPython-only application. Ben was very helpful to optimzie his library to maximum performance and provided numerous tips and tricks on how to implement it.

There is still a noticable flicker when the screen objects are changed, but it is certainly acceptable for an update of the clockface every every minute.

# Example
![20230227_153754](https://user-images.githubusercontent.com/10500110/221593639-3fc39de0-8efb-4da1-ab3b-9f07e298da30.jpg)

![20230227_153808](https://user-images.githubusercontent.com/10500110/221593715-8d877463-2181-488e-8488-2121160115bb.jpg)

