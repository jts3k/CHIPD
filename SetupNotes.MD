Step 1: Flashed CHIP OS 4.4 GUI NoLimit onto CHIP via http://flash.getchip.com/

Step 2: Installed Puredata as in [these instructions]( http://docs.getchip.com/chip.html#install-the-latest-puredata).

Step 3: Built a simple noise-generating test patch but experienced glitchy audio and an error message: tried but couldnt sync a/d/a

Step 4: Checked out [this tutorial](https://www.hackster.io/11802/c-h-i-p-midi-arpeggiating-synth-e311ab) and found that the included PD patch runs has no glitchy audio.  Determined this was because the patch manually disabled audio input.  Turns out my patch runs fine too with audio input disabled.  Culprit = found.

Step 5.  Need audio input so looking for fixes.  Tried running PD in "realtime" mode via ```pd -rt``` in terminal.  No luck.  Tried running without GUI via ```pd -nogui -rt```.  No luck.

Side note, terminal command to find the CHIP IP: ```curl ipinfo.io/ip```

Step 6.  Success!  Audio in/out running glitch-free when PD uses [this](https://www.adafruit.com/products/1475) cheap lil' USB audio interface.

Step 7.  To launch PD from terminal with all the right configs: ```pd -r 44100 -audiodev 3 -channels 1 -nogui -rt /home/chip/Documents/name-of-the-patch.pd``` (no gui) ```pd -r 44100 -audiodev 3 -channels 1 -rt /home/chip/Documents/name-of-the-patch.pd``` (with gui)
