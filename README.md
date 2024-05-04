# ubitxv6
uBitx v6.3.1 Arduino sketch
IMPORTANT: It will compile only if you place this in the Arduino's own sketch directory! This is because of the restricted places that the Arduino searches for it's include files (the headers).

- This is refactored to remove dependencies on any library except the standard Arduino libraries of SPI, I2C, EEPROM, etc.
- This works with ILI9341 display controller. The pins used by the TFT display are the same as that of the 16x2 LCD display of the previous versions.
- As the files are now split into .cpp files, the nano gui, morse reader, etc. can be reused in other projects as well

This is released under GPL v3 license.


/////////////////////////////////////

//04_sp7etd firmware update manual://
NOTE 1:
Firmware originated from v6.3.1 Arduino sketch.
For use with original ILI9341 320x240 TFT display.

Hello,
I have bought ubitx v6 couple weeks ago and at beginning I was a little disappointed with CW performance and some functionalities.
Decided to adjust it to my needs with default ILI9341 320x240 TFT display and then I have discovered beauty of this open project.

I would like to take this opportunity to thank the creator of this project Ashhar Farhan VU2ESE,
as well as all the people thanks to whom this wonderful project lives and becomes better.

Today, when I am writing this text I am after couple days (during my May's holidays) with this rig. 
During this couple days I was able to make more than 50 QSO (SSB, CW and some intercontinent DX - with 30W PA on 15m)
while adjusting the firmware.
Still some HW mods are planned to be made based on data from ubitx websites (AGC, CW audio filter, S-meter etc.).

These are some points summarizing my firmware mods:

1. jog tuning (digit tuning) implemented instead of dynamic tuning

By default jog position is set to 0.1 digit. Short knob press to shift jog single position right (eg. to 0.01),
press little longer to shift jog to the left (e.g. 1.0, 10 and 100 respectively).
Actual jog position is displayed at the bottom right corner of TFT screen.
This firmware allows for 0.01 kHz step tuning (0.05 kHz minimal was in original firmware).

2. Discovered that function checking TFT touch screen is sometimes causing audio noises (possible due to SPI).
With this firmware You can toggle TFT touch ON/OFF with ~5 seconds press and release of the knob.
Status of touch state is indicated by "t" letter at the bottom right corner of TFT screen.

3. CW keying modified - discovered that start of CW TX is cutting out first dots - starting dots were not transmitted. 
Some TX delays were commented out, CW TX is smooth now. Couple CW QSO made.

4. Additionally discovered that CW TX frequency was shifted by sidetone +/- depending if USB or LSB was selected.
This shift was commented out and CW TX occurs now on displayed/selected frequency.

5. Some cosmetic and SW stability changes
e.g. to display pop ups - some pop up messages where shifted to improve cosmetics.
Some stability issues found (original firmware was not working stable with my usb-c type arduino nano).
Seems to be OK. now.

So, now last line shows:
Shortened CW status (no units), version and origin of updated firmware, jog position and TFT touch status - presence of letter "t" indicates touch sensing ON (absence OFF). Please don't blame me for sp7etd sign. Feel free to enter Your or project creator call sign.

Summarizing, button knob has 5 functions now (depends on pressing time):
1. short press - jog position to the right
2. little longer press - jog position to the left
Jog position is displayed on the right bottom corner
3. Knob press up to 5s - do commands as in origin firmware - jump with cursor through the menu.
4. Knob press between ~5s and 10s - toggle TFT touch sensing ON/OFF - sometimes SPI noise can be heard - so toggling touch OFF can help in RX.
5. Long ~10s press until Setup window appear - as in origin firmware

Best regards
Please do not hesitate to contact with me
I will try to answer ASAP, but sometimes it can take some time...

Tomasz
sp7etd
tomekdm@interia.pl
Dabrowka 4th May 2024, Poland
