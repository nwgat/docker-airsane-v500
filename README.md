[aguslr/docker-airsane][1] for Epson V500 Scanner
==========================

[![docker-pulls](https://img.shields.io/docker/pulls/aguslr/airsane)](https://hub.docker.com/r/aguslr/airsane) [![image-size](https://img.shields.io/docker/image-size/aguslr/airsane/latest)](https://hub.docker.com/r/aguslr/airsane)


This *Docker* image sets up *AirSane* inside a docker container.

> **[AirSane][2]** is a SANE WebScan frontend that supports Apple's AirScan
> protocol. Scanners are detected automatically, and published through mDNS.


Installation
------------

To use *docker-airsane*, follow these steps:

1. Download your scanner drivers in *DEB* format into a directory named
   `./drivers`.

2. Clone and start the container:

       docker run --privileged -p 8090:8090 \
         -v /dev/bus/usb:/dev/bus/usb -v /run/dbus:/run/dbus \
         -v "${PWD}"/drivers:/opt/drivers docker.io/aguslr/airsane:latest

3. Open <http://127.0.0.1:8090> with your web browser to access your scanner.


Build locally
-------------

Instead of pulling the image from a remote repository, you can build it locally:

1. Clone the repository:

       git clone https://github.com/nwgat/docker-airsane-v500.git

2. Change into the newly created directory and use `docker-compose` to build and
   launch the container:

       cd docker-airsane-v500 && docker-compose up --build -d


[1]: https://github.com/aguslr/docker-airsane
[2]: https://github.com/SimulPiscator/AirSane
