linuxcnc-cncdudez-2012
======================

LinuxCNC configuration for the CNCDudez 2012 Desktop Mini Muscle CNC Machine




CW5045 Microstepping Drivers
----------------------------

http://www.ukcnc.info/forums/showthread.php?1202-Stepper-motor-heat-sinks

> Even though the motors we use on the CNC Mini Muscle Machine are rated
> at 4.2 amps I set the driver at around 3.7 amps to play safe. So even
> going slow speeds where the current is at it's peek then they should
> still not get to boiling point as such.



Configuration for the microsteping driver:

| DIP Switch | Setting | Meaning       |
|------------|---------|---------------|
| SW1        | Off     | 3.7 Amps      |
| SW2        | **On**  | 3.7 Amps      |
| SW3        | Off     | 3.7 Amps      |
| SW4        | **On**  | Full Current  |
| SW5        | Off     | 10 microsteps |
| SW6        | Off     | 10 microsteps |
| SW7        | **On**  | 10 microsteps |
| SW8        | **On**  | 10 microsteps |

More information in the datasheet:
http://cnc4you.co.uk/resources/CW5045.pdf

Timing settings:

| Setting              | Value       |
|----------------------|-------------|
| **Step Time**        | 2000 ns     |
| **Step Space**       | 8000 ns     |
| **Direction Hold**   | 5000 ns     |
| **Direction Setup**  | 5000 ns     |
| **Steps on**         | Rising Edge |

More here: http://wiki.linuxcnc.org/cgi-bin/wiki.pl?CW5045


Parallel Port configuration
---------------------------

I am using a HG08 Parallel Port 'breakout board':
http://www.cnc4you.co.uk/index.php?route=product/product&product_id=300

All pins are inverted.


| Pin | Direction | Breakout Label | Linux CNC Description |
|-----|-----------|----------------|-----------------------|
| 1   | Out       | EN             | ESTOP Out             |
| 2   | Out       | CKA            | X-Axis Step           |
| 3   | Out       | CWA            | X-Axis Direction      |
| 4   | Out       | CKB            | Y-Axis Step           |
| 5   | Out       | CWB            | Y-Axis Direction      |
| 6   | Out       | CKC            | Z-Axis Step           |
| 7   | Out       | CWC            | Z-Axis Direction      |
| 8   | Out       | CKD            | Unused                |
| 9   | Out       | CWD            | Unused                |
| 10  | In        | IN4            | ESTOP In              |
| 11  | In        | IN3            | Both Limit + Home X   |
| 12  | In        | IN2            | Both Limit + Home Y   |
| 13  | In        | IN1            | Both Limit + Home Z   |
| 14  | Out       | RLY            | Spindle On            |
| 15  | In        | IN5            | Probe In              |


Parallet Port breakout board datasheet here:
https://github.com/njh/linuxcnc-cncdudez-2012/raw/master/docs/HG08.pdf


Stepper Motor Wiring
--------------------

I am using 57HS82-3008B 2.2Nm Stepper Motors, wired in Bi-polar parallel mode.
They are connected to the control box using 4-pin XLRs.

![XLR 4 Pinout](https://github.com/njh/linuxcnc-cncdudez-2012/raw/master/docs/xlr4_stepper.png)

| XLR Pin | Description | Cable Colour | Stepper Motor colour |
|---------|-------------|--------------|----------------------|
| 1       | A+          | White        | Red + Blue           |
| 2       | A-          | Yellow       | Yellow + Black       |
| 3       | B+          | Brown        | White + Brown        |
| 4       | B-          | Green        | Orange + Green       |

Stepper motor datasheet here:
https://github.com/njh/linuxcnc-cncdudez-2012/raw/master/docs/57HS82-3008B.pdf



Other Notes
-----------

Steps per revolution: 200
Driver Micro-stepping: 10
Pully Teeth (Z axis): 1.0 : 1.0
Ballscrew Pitch: 4mm per revolution
