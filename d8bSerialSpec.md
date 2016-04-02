# d8b Serial Commands #

Here I will post what I found about the commands the d8b sends to the console an vice-versa,


## console to D8B CPU commands ##

Faders.

> the faders commands consist of 4 hex numbers followed by a "f", where the
> first byte is the channel(from 0x00 to 0x18, where 0x00 is channel 1 and
> 0x18 is the master fader), and the last byte the fader value (from 00 to
> FF), example:

> "035Ff" ,this mean: move fader from channel 4 to value 5F

Buttons:

> buttons codes consist of hex numbers followed by a "s" or "u", where "s"
> means pressed and "u" means released,example:

> "05Es" means button with code "05E" pressed

> Note: there is a file called "switch.txt" in the Mackie OS system
> directory that shows the codes of each button,

VPots:

> VPots movements are 4 hex numbers followed by a "v", the first byte is
> the channel (from 0x00 channel 1 to 0x17 channel 24) and the second byte
> indicates the direction: 0x01 is left, 0x4E is right, example:

> "0A4Ev" means: move vpot channel 10 to the Right,

> Note: I assume each step is from 1 to 255,

## D8B CPU to console commands ##

Faders:
> the faders work in the same way that from d8b CPU to console,

LEDs:
> when the user press a button, the d8b CPU sends back a code to turn
> on/off the corresponding LED,(including the LEDs from the VPots)
> almost all button LEDs codes are included in the Mackie OS system file
> called "led.txt", except the LEDs from the VPots, which I had to find
> myself, I will post them later.

> then, after these codes, there are 3 posible commands(at least these are
> what I found) :

> "i" : turn LED ON

> "j" : Turn LED OFF

> "k" : Turn LED ON and keep it blinking (like the REC button LEDs)

> example: "108k" Turns the REC button from channel 2 and keep it blinking

Meters:

> ?? still have not found anything about this.










