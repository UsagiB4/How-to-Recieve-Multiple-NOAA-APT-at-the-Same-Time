## How I capture Multiple Passes of NOAA Weather Sat and Decode Them

NOAA APT is one of the most easiest and most beginner friendly Space Data you can access. Even for a beginner, it's very easy to setup the ground station for APT and get their first images from NOAA Sats (15, 18, 19).

### All you need is:
***Hardware :***
- A V-dipole antenna made for 137MHz.
- RTL-SDR
- LNA (Really helpful to get the signal even from a low pass)

***Sofware :***
- SDR++ (To recieve and record RF signal)
- Gpredict (For getting satellite schedules)
- SatDump (For Decoding the Signal and get images)

>> Note: As a linux user, I have shown the softwares that works with my machine. It should work with Windows and Mac too.

### Getting started:
If you are not familier with this and a complete beginner, please visit [this article first](https://www.a-centauri.com/articoli/noaa-poes-satellites-reception). It's a really amazing guide for beginners to follow.

## Getting Multiple Passes of NOAA at the same time:
Before recording data, I setup my ***SDR++*** as below:
- *From `Source` option*
  - Select `2.048MHz` from **Sample Rate**
  - Check The **RTL AGC**
  - Increase the Gain as much as you need but don't over do it.
- *From `Radio` option*
  - Select **NFM**
  - Bandwidth **50000** (highest)
  - Check the **IF Noise Reduction** and Select `NOAA APT`
- *From `Recorder` option*
  - Select **Baseband**
  - Select output directory.
  - Sample type must be **int16**

That will be all.
When The satellites passes over the head, Hit record. This will generate a large `.wav` file.