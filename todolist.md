# TODO LIST #
  * "DREAM" : **try to find a way to make a long lcd screen** that can be put  in the faders section and can be programmed to act like the mackie MCU LCD screen to display channel names and other cool features...

  * **implement different non-mcu user-configurable layers**
> > so an User could map each button/fader/pot to whatever he wants so he can send non-MCU MIDI messages(like CC messages) to DAW specific functions or use the MIDI-learn to map each vpot or fader to different plugins in each layer, try to make it support N layers


  * **DONE** **implement the led meters**
  * **almost DONE** **implement the time display**
  * **implement the display messages**
  * **DONE** **implement vpots**
  * **DONE** **implement feedback**
> > (when i press a button, the program must send a command to turn on the corresponding leds)
  * **almost DONE** **implement the mcu 2 d8b translation on switches**
> > (for now only the faders work)
> > it's only matter of mapping the midi commands in switch.txt nd leds.txt

  * **save the whole d8b buttons and faders config on each mode**
> > ( for now onle the faders get saved)
> > for d8b mode, better the cpu recall all of them
> > for daw mode it would be needed to save each led and fader

  * **implement the faders and buttons on other applications diferent of a DAW**
> > (example: the audio interface config window ) ,save a config for each "window"
  * **keep receiving and saving states from all ports**
> > (for now, when in DAW mode, the program ignores the d8b CPU data and viceversa )
  * **when moving faders, send a message incrementing the values from the "actual" value to the "target" value**
> > (example: if the value is at 00, and a FF is received, instead of turning directly to FF, send a lot of messages incrementing the value until FF is reached , the value increment depends of the max messages/time support, so the program doesn't get saturated or loses messages for doing this)

  * **make user-configurable which buttons/faders will still work on the d8b CPU then in DAW mode**
> > so for example: one can use the first 8 channels to control the d8b CPU and 16-24 to control the DAW,or control main or headphones volume in DAW Mode,without needing to change to d8b Mode
  * **DONE** **implement transport control**
  * **use MidiOutLongMsg instead of MidiOutShortMsg**
  * **only send last fader value**
> > when 2 or more same fader movement received in the same buffer, just send the last value (in opposition to the incremental messages option)
  * **use cros-plattform libraries for Serial and MIDI ports control (also threads)**
> > for now, the code only works in W!nd0ws :(
  * **hide main window**
> > at now it is a console window, it would be good if it could be hidden  or put in tray icon mode, but again, it would be only for w!nd0ws