# Bobble HAT

A Go library to support Raspberry Pi HATs (Hardware Attached on Top), starting with the [Sense HAT](https://www.raspberrypi.org/products/sense-hat/).


### Go on Pi

How to prepare a MicroSD card for Go development on a Raspberry Pi.

On your Mac/PC:

* Download [Raspian Jessie Lite](https://www.raspberrypi.org/downloads/raspbian/)
* Make a MicroSD card with [Apple Pi Baker for Mac](
http://www.tweaking4all.com/hardware/raspberry-pi/macosx-apple-pi-baker/) or [follow these instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md).

Power up the Pi with a Keyboard and TV/Monitor attached:

* Use `sudo raspi-config` to configure the Pi.
    - Expand the file system before installing further apps.
    - Set your internationalization options
    - Advanced options, SSH, enable
    - Reboot when done `sudo reboot`

* Update all the things
    - `sudo apt-get update`
    - `sudo apt-get upgrade`

* Install Go 1.6
    - [Download Go for Linux ARM](https://golang.org/dl/) (armv6l)
        eg. `curl -O https://storage.googleapis.com/golang/go1.6beta2.linux-armv6l.tar.gz`
    - Extract Go following the [installation instructions](https://golang.org/doc/install).
    - Use `nano ~/.profile` to edit your startup script to configure your PATH and GOPATH:
    
        ```
        export PATH=$PATH:/usr/local/go/bin
        export GOPATH=$HOME
        ```
    - Run `source ~/.profile` or reboot to pick up the changes.
    - Run `go version` to check that everything is installed.

* Install Git to download source code
    - `sudo apt-get install git`

* [Configure WiFi](https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md) if necessary.

* SSH from your Mac/PC
    * Jessie has [avahi-daemon](http://www.howtogeek.com/167190/how-and-why-to-assign-the-.local-domain-to-your-raspberry-pi/) for Bonjour networking. 
        - Use `ssh pi@raspberrypi.local`
        - The default password is `raspberry`
    * Otherwise you can use the IP address `ssh pi@<IP>`. See [SSH instructions](https://www.raspberrypi.org/documentation/remote-access/ssh/).

### Related Projects

* [Gobot](http://gobot.io/)
* [EMBD](http://embd.kidoman.io/)

