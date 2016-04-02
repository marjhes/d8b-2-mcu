# Introduction #

I will be writting here the project current status

# Details #


  * NEW: all 24 channel work, with button leds feedback (including vpots) and led meters(still testing for some bugs)
  * the transport buttons work and jog wheel/scrub/zoom
  * the remaining mcu buttons is just matter of mapping to a specific d8b buttons
  * just implemented the time display, for now it works, just needs to clear the displays when changing from minutes/secs to bars/beats
  * LED meters work, just testing on Reaper, it doesn't send clear led meters commands, tested in FLstudio and it worked, maybe need to put a timer to turn led meters off when the DAW stopped sending update commands
  * added the bank+ and bank- button, when you press bank+ it will simulate 3 bank+ presses, so It will change the faders from 1-24 to 24-48, acting like a second layer of faders
  * planning to add a new "free" non-mcu layer where you can map each fader/vpot/button to whatever you want, example DAW specific functions or use MIDI-learn (in theory there could be unlimited layers) just need to keep a cache of each layer led status for recalling when changing layer












