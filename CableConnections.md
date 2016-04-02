# Cable Connections #

![http://www.accesscomms.com.au/images/reference/Dsub/DB25pinout.jpg](http://www.accesscomms.com.au/images/reference/Dsub/DB25pinout.jpg)

DB9 MALE:

![http://www.zytrax.com/images/rs232_db9.gif](http://www.zytrax.com/images/rs232_db9.gif)

DB9 FEMALE:

![http://www.zytrax.com/images/rs232_db9_f.gif](http://www.zytrax.com/images/rs232_db9_f.gif)

DB25 PINOUT (CPU MALE CONNECTOR)
> .1 = COM1.1
.14 = COM1.2 RECEIVED DATA
> .2 = COM1.3 TRANSMITTED DATA
.15 = COM1.4
> .3 = COM1.5 GROUND
.16 = COM1.6

> .4 = COM1.7
.17 = COM1.8
> .5 = COM1.9
.18
> .6 = COM2.1
.19 = COM2.2 RECEIVED DATA
> .7 = COM2.3 TRANSMITTED DATA
.20 = COM2.3
> .8 = COM2.4
.21 = COM2.5 GROUND
> .9 = COM2.6
.22 = COM2.7
> .10= COM2.8
.23 = COM2.9
> .11
.24
> .12
.25
> .13

DB25 PINOUT (CONSOLE DATA FEMALE CONNECTOR)

> .1 = COM1.1
.14 = COM1.3 TRANSMITTED DATA  // NOTE THE SIGNALS HERE ARE
> .2 = COM1.2 RECEIVED    DATA  // INVERTED,
.15 = COM1.4
> .3 = COM1.5 GROUND
.16 = COM1.6

> .4 = COM1.7
.17 = COM1.8
> .5 = COM1.9
.18
> .6 = COM2.1
.19 = COM2.3 TRANSMITTED DATA //NOTE THE SIGNALS HERE ARE
> .7 = COM2.2 RECEIVED    DATA //INVERTED
.20 = COM2.3
> .8 = COM2.4
.21 = COM2.5 GROUND
> .9 = COM2.6
.22 = COM2.7
> .10= COM2.8
.23 = COM2.9
> .11
.24
> .12
.25
> .13


NOTE: the wires from com2 port are connected directly from the d8b CPU to the console data port, matching the  same pin number(only check where the pin 1 is, the pin numbers are inverted in male an female connectors, check images) and the wires from port COM1 , connected from the d8b CPU to the serial/USB interface, checking DB25  transmit data (DB25 Pin 2 ) is connected to DB9  received data ( DB9 Pin 2) And DB25 PIN 14 To DB9 Pin 2 and the rest of the pins to the corresponding pins listed, then connecting the other serial/USB intergace to the desk DB25 Port, Checking DB9 Transmit Data Pin 3 Is connected to DB25 Received data Pin 2 And DB9 Received Data Pin 2 To DB25 Transmit Data Pin 14, Note that Receive/transmit data pins are different in the d8b CPU DB25 Male Port and desk DB25 Female Port, thats because when you use a straight DB25 Cable(like the "console data" cable ) the Transmit data Pin from Serial Port on the CPU goes to the Received data Pin on the Desk,
> (I hope you understand... yes even I got confused myself)

Oh and be sure to connect the Ground Pins to the corresponding pins, I don't know If is enough if you only connect the Transmit/receive/ground pins or you need to connect all Ports cables, maybe it would work, I haven't tried yet,


I'll try to make a "graphic" diagram later to show clearly how it is connected

