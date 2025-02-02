# adsb-feeder-image

Easy to use turn-key SD card image for a number of single board computers (so far Raspberry Pi3/4, Libre Computing Le Potato, and Asus Tinkerboard)
to run a complete ADS-B feeder
that feeds the large "open data" ADS-B flight trackers (currently [adsb.lol](http://adsb.lol), [adsb.one](http://adsb.one), [adsb.fi](http://adsb.fi),
[planespotters.net](http://planespotters.net), and [TheAirTraffic.com](http://theairtraffic.com).

The goal of this project is to make things as simple as possible for the non-technical user.

- buy one of the supported boards (at least the Le Potato seems to be easily and cheaply available in most places)
- invest in a decent power supply - while many of these can be driven from a powered hub or a cheap 'charger' plug, not having a stable 5V power
source tends to be the biggest causes ofissues with these SBC
- get an SDR and antenna. There are many many choices. Availability may differe depending on where you are. But often the 'green' RadarBox SDR and
an indoor or (much better) outdoor antenna is all you need
- download the latest image from the Release section
- use a tool like the [Raspberry Pi Imager](https://github.com/raspberrypi/rpi-imager/releases) to write the image to a µSD card on your computer
- if doing this with the RPi image, only use the 'wifi setup' option to make sure the image can connect to your wifi - everything else should be
kept unchanged
- boot from the image
- wait a couple of minutes for the initial boot to complete, then connect to the [ADSB-PI Setup Page](http://adsb-pi.local:5000) -- this link
_should_ work to find the freshly booted system on your local network - assuming you have a reasonably standard setup with mDNS enabled.
Otherwise you'll need to figure out its IP address which is a lot harder...
- on the setup website enter the latitude, longitude, and elevation of your receiver
- there's a convenient button to get the correct time zone from your browser
- click on Submit and then be patient while everything gets installed and setup - depending on your internet speed this could take several minutes
- once the setup is completed, it should automatically forward you to your local [feeder website](http://adsb-pi.local:8080) and you should see the aircraft that you
are tracking. And in the background, all these plane positions are fed to the main open data ADS-B flight trackers.


# for developers

This repo actually contains the scripting to create the SD card image for some common SBCs to run an ADS-B feeder. And as 'releases' it publishes such images.

This requires [CustomPiOS](https://github.com/guysoft/CustomPiOS) - unpack this next to the `CustomPiOS` folder in order for the scripts to work.

I'll add more detail here shortly 🤣
