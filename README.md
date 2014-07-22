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

All pins are inverted.

| Pin | Breakout Label | Linux CNC Description |
|-----|----------------|-----------------------|
| 1   | EN             | ESTOP Out             |
| 2   | CKA            | X-Axis Step           |
| 3   | CWA            | X-Axis Direction      |
| 4   | CKB            | Y-Axis Step           |
| 5   | CWB            | Y-Axis Direction      |
| 6   | CKC            | Z-Axis Step           |
| 7   | CWC            | Z-Axis Direction      |
| 8   | CKD            | Unused                |
| 9   | CWD            | Unused                |
| 10  | IN4            | ESTOP In              |
| 11  | IN3            | Both Limit + Home X   |
| 12  | IN2            | Both Limit + Home Y   |
| 13  | IN1            | Both Limit + Home Z   |
| 14  | RLY            | Spindle On            |
| 15  | IN5            | Probe In              |


Parallet Port breakout board datasheet here:
http://cnc4you.co.uk/resources/Breakout%20board%20HG08.pdf



