# partypi

Here are a few python scripts to make your [unicorn phat](https://shop.pimoroni.com/products/unicorn-phat) into a badge. If I was better at scripting, I would provide one of those fancy setup scripts that would do all the things on your raspberry pi, but I'm not so... here are some sort of manual instructions.

## Setup

1. Set up your raspberry pi by flashing the [operating system](https://www.raspberrypi.org/downloads/raspberry-pi-os/) onto an SD card. I suggest Lite since we won't be using a screen but you do you.
2. Set up the pi to connect to your network following [these instructions](https://www.raspberrypi.org/documentation/configuration/wireless/headless.md).
3. While you're adding `wpa_supplicant.conf`, also create an empty file called `ssh`. It will enable connecting via SSH.
4. Connect to it via SSH. Run `ssh pi@raspberrypi.local` and use the password `raspberry`.
5. Follow the instructions to install the Pimoroni [unicorn hat libraries here](https://github.com/pimoroni/unicorn-hat).
6. Move the partypi python scripts from your computer to your raspberry pi. You can [use SFTP to move files](https://www.raspberrypi.org/documentation/remote-access/ssh/sftp.md) between your computer and the pi.
7. Run `sudo python party.py` or `sudo python radtag.py`.

## More things to try

### Running a script on boot

On mine, I set up cron some time ago to run `party.py` at boot. Definitely handy for a badge. This way the blinky lights start when it's powered up.

### Auto hotspot detection and switching

I followed this guide to set up auto hotspot detection. When I'm at home, it connects to my network. When I'm out and about, it creates its own. This lets me give it commands with my phone if I want to change what is running.