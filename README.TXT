wiringPi version 2
===================

This is an UN-OFFICIAL version of wiringPi from drogon.net. Please go to http://wiringpi.com for everithing!
I've cloned this for my purposes only because I need to made mods that have to be reflected in various distro's.


Please note that the official way to get wiringPi is via git from
git.drogon.net and not GitHub.

ie.

  git clone git://git.drogon.net/wiringPi

The version of wiringPi held on GitHub by "Gadgetoid" is used to build the
wiringPython, Ruby, Perl, etc. wrappers for these other languages. This
version may lag the official Drogon release.  Pull requests may not be
accepted to Github....

Please see

  http://wiringpi.com/

for the official documentation, etc. and the best way to submit bug reports, etc.
is by sending an email to projects@drogon.net

Thanks!

  -Gordon
  
Sumotoy addendum...
Since I'm coming from microcontrollers I was shocked about the business around Raspberry Pi. This board it's really cheap but after selling more than one million units
it should cost much less! Aniway, all stuff around Raspberry cost a fortune, speaking about plastic cases (12 -> 200 dollars or more!), preformatted SD card, wires, etc.
<br>Arduino has shields, not cheap really but most of the time easy to rebuild because opensource.<br> Raspberry has expansion cards, most of the time not open source and no schematics,
absourdely expensive and no design at all! Take an example:
PiFace costs more than 20 pounds and basically it's just an MCP23s017 and a buffer plus a couple of cheap relays and some other passive component, you can build this in 20 minutes at home on a breadboard or similar and there's nothing special, just plain datasheet applied.
There's no way to find out the schematics... why??? This circuit it's used millions of times for many projects as is!
Did you want to make one?
MCP23s08/MCP23008 connections

                    MCP23S17 (dip)
                           
        IN0       -> [|--U--|] -> OUT 7
        IN1       -> [|     |] -> OUT 6
        IN2       -> [|     |] -> OUT 5
        IN3       -> [|     |] -> OUT 4
        IN4       -> [|     |] -> OUT 3
        IN5       -> [|     |] -> OUT 2
        IN6       -> [|     |] -> OUT 1
        IN7       -> [|     |] -> OUT 0
        +3v3      => [|     |] -> INT A (unconnected)
        ground    => [|     |] -> INT B (GPIO-25)
    cs (GPIO8)    *> [|     |] <= +3v3
    sck (GPIO11)  *> [|     |] <= A2 (ground or +3v3)
    mosi (GPIO10) *> [|     |] <= A1 (ground or +3v3)
    miso (GPIO9)  <* [|_____|] <= A0 (ground or +3v3)
    

Addressing: A0,A1,A2 to ground = 0x20 (see datasheet)
Do I need the buffer chip? Yes if you want drive several relays, remember that MCP can give you only 125mA max so if you want to connect some leds at outputs select a 680Ohm resistor to keep current flow low.
<br>Surprised? Did you think in PiFace there's a lot more? In hardware side NO, it's just this!
Ok, if you want a fully PiFace just connect 4 buttons in inputs 0 to 3, an buffer chip (or just 2 transistors) on output 0,1 and a bounch of leds in the other outs!
Using wirePi give you much more possibilities since you can decide how many pins must be outs and hom many inputs and so on.


