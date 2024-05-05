# G25 Pedals and Shifter
Arduino-based USB interface for Logitech G25 Pedals and Shifter:

## What's difference between this and Cheroukee's work?
* This code supports only Arduino Pro Micro 5V/16MHz ATmega32U4!!!
* Added DPad functionality
* Added G25 Pedals Axis values like on G25 Wheel
* Changed Axis to Rx,Ry,Rz
* Cleared code from Teensy, and unused buttons/axis

## Required Parts/Materials

* [SparkFun Pro Micro](https://www.sparkfun.com/products/12640) or clone (must be a 5V/16MHz ATmega32U4 with onboard USB)
* [DB9 Connectors](http://www.amazon.com/Female-Male-Solder-Adapter-Connectors/dp/B008MU0OR4/ref=sr_1_1?ie=UTF8&qid=1457291922&sr=8-1&keywords=db9+connectors) 1 male, 1 female
* Hookup wire in assorted colors
* Some kind of project box

## Assembly

![pinout](https://raw.githubusercontent.com/Ziome3eg/G25_Pedals_and_Shifter/master/pinout.png)

## Firmware

Open the .ino file in the Arduino IDE, select the proper board type and COM port under "Tools" (you will need to install the [SparkFun board library](https://github.com/sparkfun/Arduino_Boards)).  You will probably need to adjust the thresholds for SHIFTER_XAXIS_12 and friends, the values that decide which gear you're in based on the x/y axis of the shifter.  Change the `#define DEBUG_SERIAL 0
#define DEBUG_SHIFTER 0` to `#define DEBUG_SERIAL 1
#define DEBUG_SHIFTER 1`.

## Calibration and Configration

The pedals are self-calibrating, meaning the system determines the min/max value for each pedal in realtime.  What this means is that each time the device is powered on, you'll need to push each of the three pedals all the way to the floor once to let it know what the maximums are.

When configuring the shifter and buttons, gears 1 - 6 are buttons 2 - 7, reverse is button 8 (button 1 is SHIFTER NEUTRAL but it doesn't change its state)
