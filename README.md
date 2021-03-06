
![2021-09-14](https://user-images.githubusercontent.com/9722781/133297728-5d1a6935-718c-42a2-8ce1-6959e1012b03.jpg)
![IMG_20211009_104827](https://user-images.githubusercontent.com/9722781/136651467-f8c7f292-17d4-425b-af63-6b4528d9850e.jpg)
![IMG_20211009_103845](https://user-images.githubusercontent.com/9722781/136651468-285830e9-37b0-4a31-923c-8c0b020c9f74.jpg)
![IMG_20211009_103855](https://user-images.githubusercontent.com/9722781/136651470-6fefe74c-c7fe-49d6-b26a-85049be431f5.jpg)
![2021-10-09 PCB_SX1278_Micro](https://user-images.githubusercontent.com/9722781/136651522-ede4b76a-fefe-42e4-91b5-9781e72c554d.png)
![IMG_20211012_212754](https://user-images.githubusercontent.com/9722781/137446925-404774f3-f50b-4367-bfe1-a0e923a9ad1d.jpg)


# SX1278
Aprs using Lora sx1278

Clone of this project, using a SX1278 Lora module or just the IC SX1278 as aprs tx, ALL credit goes to https://github.com/DO4AS/jufo-project-radiosonde
I have only made the pcb:s and edited the fw in a small way that fits my needs.

PCB for both LORA sx1278 module and barebone 1278 ic, make sure you get the correct module, at least 4 Lora models avalible with different pinout.

The sketch on the 328 works at 8Mhz or 16Mhz, Im using 8Mhz to save 5mA compared to 16Mhz

Fuses for 328: FD D9 FE

1278-Micro_2021-10-09.zip is the CAM files for pcb production/order

Latest PCB have the option for tcxo drive of the 1278, but the standard 32Mhz xo footprint can stil be used, gps antenna moved to the "top" + some small tweaks and fixes.

Adjust the "const float baud_adj = 0.952;" setting for 3 or 4 "strokes" in Direwolf, see info here https://forums.qrz.com/index.php?threads%2Fdirewolf-aprs-output.600522%2F&fbclid=IwAR0wUjOZmizGcujBzJqjSxanfelDZbqJ7fJmPpOwpc3_y3LSQ0mrltJrEoM   
I have the best decode rate with 0.950 - 0.964 depending on xo/tcxo used, so you need to tweek this for every board.

Also test the transmitted audio against this program - AFSK1200, if it decodes the audio it should maximize the chanses of your signal to be decoded while in flight
https://sourceforge.net/projects/qtmm/

DG4NOB version incorporates more telemetry readings like Temp from internal 328 sensor, Voltage, Vertical speed in m/s etc

TBTracker and horusbinary_tracker use the same pcb layout and is 100% compatible with the above, those fw transmitt, 4FSK, RTTY and Lora, original authors git at  https://github.com/RoelKroes  with small adjustment to fit "my" pcb layout
