# DIREWOLF ADC Level
DIREWOLF AX25 SW MODEM is commonly used in Amateur Radio. For best decoding, it is important to set the level of the incoming packets correctly.

First we tune to an active channel, like APRS, and accumulate received packets using the command:

tail -f /var/log/direwolf/direwolf.log > aprs.log

Inspecting the log, we need to extract the audio level from each packet; audio level = 26 for this packet:

Jul 18 13:45:46 K7UDR direwolf[549]: Digipeater VE7SLC-7 audio level = 26(11/19)   [NONE]   ||||_____
Jul 18 13:45:46 K7UDR direwolf[549]: [1.1] WA7EBH-15>APTW01,VE7SLC-7*,WIDE2:_07191349c347s005g006t068r000p000P000h73b10246tU2k
Jul 18 13:45:46 K7UDR direwolf[549]: Positionless Weather Report, VAN, Byons WXTrac
Jul 18 13:45:46 K7UDR direwolf[549]: wind 5.0 mph, direction 347, gust 6, temperature 68, rain 0.00 in last hour, rain 0.00 in last 24 hours, rain 0.00 since midnight, humidity 73, barometer 30.26, "tU2k"

Then we scan each packet to detrmine MIN, MAX and AVG.
