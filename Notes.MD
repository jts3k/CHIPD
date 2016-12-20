Step 1: Flashed CHIP OS 4.4 GUI NoLimit onto CHIP via http://flash.getchip.com/

Step 2: Installed Puredata as in these instructions: http://docs.getchip.com/chip.html#install-the-latest-puredata

Step 3: Built a simple noise-generating test patch but experienced glitchy audio and an error message: tried but couldnt sync a/d/a

Step 4: Checked out this tutorial and found that the included PD patch runs has no glitchy audio.  Determined this was because the patch manually disabled audio input.  Turns out my patch runs fine too with audio input disabled.

