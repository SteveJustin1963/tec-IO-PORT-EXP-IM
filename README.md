# tec-IO-PORT-EXP-IM
TEC-1 32 Port Select Expansion daughter board


Ian McLean
Amceaptril S2poemt1gnr, socrehnd2td02ad0  · 
32 Port Expansion for TEC-1 daughter board

This is my proposed circuit - just a stock standard use of 138 decoders and 1/2 of a 139 decoder for building a larger decoder as per datasheet spec.

Ian McLean
Author
Why so many ports? Answer one - Why not?! Answer two - because I would like to build a 16x8 display (or larger) with every LED individually addressable and latch-able - i.e. no multiplexing required, and therefore a much much easier display to drive, and consequently a display with even brightness on all LEDs. A 16x8 will require 16 ports.
Yes I know I could use a modern LED matrix driver chip and save all those latches (and ports), but I am going old-school, and trying this out instead.
 · Reply · Share · 1y · Edited
Paul Antoine
There's a reason I love GALs/CPLDs...
 · Reply · Share · 1y
Ian McLean
Author
Paul Antoine Great option. Any suggestions for a suitable chip? This would be a great CPLD learning project - an easy project at that. I don't have any experience outside of the 16V8/20V8 and 22V10 GALs, neither of which are large enough to make a 5 to… See More
 · Reply · Share · 1y
Mark Jelic

Ian McLean that is going to be an expensive display!
You know what I to reckon would be interesting to make: an LED display circuit that has its own scan routine without having the CPU involved. Would need some way to read the data (in your case, 16 bytes) while the CPU can still write data to that same 8 bytes...
Ooh, just had a thought! TWO sets of 16 bytes that as far as the CPU is concerned, writes to one location, but in fact writes to bank A. When the CPU finishes writing (CE off) a latch flips so that the next time data is written it is going to bank B. Meanwhile the video processor is multiplexing the data in Bank A!! When data is written next time to bank B, video loop uses data from B. Bam!!
I bet there is an official name for this idea and some historic smarty pants will say “Der, that’s how blah blah video works!”... yeah well, I just came up with this idea right here right now! No patent infringement possible and I give the idea out to the open! Sue me! 😂
 · Reply · Share · 1y · Edited
Ian McLean
Author
Mark Jelic Expensive is a relative thing these days. I just ordered 8 x 74LS273 chips from Element14 (yes they still have them!) for $1.43 each. Yes, so 16 of these will be about $23 to build such a display.
With parts so cheap these days, it tempts me… See More
 · Reply · Share · 1y
Mark Jelic

Ian McLean I can dig it. 👍🏻
I on the other hand want to make a display... saaaay... a 24x16 (made out of six of those little 8x8 modules)...
B… See More
 · Reply · Share · 1y
Ian McLean
Author
All said and done, regardless of how I end up driving the LED display, there is still no harm in decoding 32 ports on the TEC - because I can 😉
 · Reply · Share · 1y
Ian McLean
Author
Mark Jelic I think displays this big, 24x16 or bigger and you are into shift register territory, as Andrew McMeikan below has suggested. I believe this is the way many commercial displays are done or at least prior to dedicated LED matrix driver chips … See More
 · Reply · Share · 1y
Mark Jelic

Ian McLean Please explain! (I know what a shift register is, but how do you use one when making displays?)
 · Reply · Share · 1y
Andrew McMeikan
There are shift registers dedicated for leds. Then you just have one resistor to set the current. Otherwise just use outputs as you would a latch. I have done this for a living so I can give you some pointers, I will have to avoid giving out specifics.
 · Reply · Share · 1y
Mark Jelic

Andrew McMeikan are you talking about a serial to parallel shift register?
 · Reply · Share · 1y
Andrew McMeikan
Mark, yep, like the hc595. I used to use mbi chips, but there are many to choose from.
 · Reply · Share · 1y
Paul Antoine
595s are really easy to work with in my experience...

Andrew McMeikan
Shift register would be better, a lot easier to expand

