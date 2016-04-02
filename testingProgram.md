# Introduction #

```
/*
first you edit conf/d8b_conf.txt , the port parameters is something like: "-p x y z" where:
"x" is the d8b console port, "y" is the d8b CPU console port, and "z" is a virtual port
I created 2 splitters in VSPE  and a Connector, something like this:

COM11->COM13 splitter
COM16->COM14 splitter
COM15                   connector

where COM11 and COM16 are my physical seria ports,
then i put in the file "-p 12 13 14" cause COM1 is
 port number 0,COM2 is port number 1...etc then my
 ports used are "-p 12 13 14" = COM13,COM14,COM15 = console,CPU,virtualPort

then edit conf/d8b_2_daw_conf.txt something similar 
to "-p a b c d e f g" that means "-p MCUMidiOut1
 Extender1MidiOut2 Extender2MidiOut3 MCUMidiIn1
 Extender1MidiIn2 Extender2MidiIn3 VirtualSerialPort"
the Virtual serial Port is the same you configured 
in d8b_conf.txt
the MIDI ports are numbered from 0 to N in the same
 order as they appear in you DAW (MIDI Mapper doesn't
 count, it counts as -1) anyway I will tell you later
 how to list the midi devices and port numbers in my program....


FIRST: Run d8b.exe , It will act as a bridge between
 the d8b console and the CPU, then when It finally 
loads ... you can use the following comands:

/printoutput N    : if n is 1 it will print the data
 received from the console to the CPU and some debug
 info, a 0 will disable output printing, I dont recommend
 using it, better use you external program to sniff the data

/send N DATA : send DATA to port N,( N is the port number, COM1=0,COM2=1,etc) (used only for testing purposes)

/demo N : if 1, it will move the faders in a sine wave
 form, use only for fun! :p disable with /demo 0

and the most important:

/detect N, if 1 it will start to detect the buttons and
 the "special combination" to enter DAW Mode: SHIFT+MASTER,
 when it enters in DAW Mode, It will load the defaul
 values of faders from last values.txt (for now is
 just a sine wave form) and will stop receiving commands
 from the CPU, it instead will send commands to the
 Virtual Port. pressing again SHIFT+MASTER will enter
 again in normal D8B Mode

/q or /quit quits the application (it correctly close the ports)

Then. you can run the program d8b_2_daw.exe, its the
 translator program, it receives d8b commands from the
 virtual serial port and translates to MCU MIDI commands,
 and send the MIDI data through the respective MIDI Out
 devices...  and Translated the MIDI in data to the 
Virtual serial port here i a list of commands:

/listmidi here you can list the midi devices and the 
numbers (these are the numbers used in the
 "d8b_2_daw_conf.txt" file

/midisend chan HH HH HH sends midi data,chan is 
from 0 to 24, if it is a fader/mute/solo/select/pot
 value it will detec the respective midi port used,
 if is a general command, use channel 0 (example a 
start/stop command) and HH HH HH is the command to 
send, example : /sendmidi 0 90 5E 7F sends the play
 command to the DAW.

/print N if 1 prints some debug info as also prints
 the data sent/received

/q or /quit quits the application (it correctly close the ports)

tip: you can modify the leds.txt and switch.txt file to map the rest of the buttons to MCU midi commands, just after the button description
you neet to space 3 tabs, then put the channel number (0 if is not related to the channel strip) then another tab, then the MCU command when pressed (separated by spaces) , then the a "," symbol and then
the MCU command when released, I mapped almost all the select/mute/solo/rec buttons and some transport buttons (play,stop,rew,fwd,scrub,zoom) just check the Mcu DOcumentation here in the wiki, have fun testing it!


*/
```