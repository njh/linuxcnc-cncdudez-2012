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

