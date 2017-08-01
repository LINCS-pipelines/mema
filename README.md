### mema: Docker container for running MEMA vignettes in RStudio

This mema docker image was built based on the validated MEMA R package v1.0.1 (released on 2017-05-16) to run all the R code in the vignettes provided by MEP-LINCS on 2017-05-17 at [`https://github.com/MEP-LINCS/MEMA/tree/master/vignettes`](https://github.com/MEP-LINCS/MEMA/tree/master/vignettes) inside a virtual RStudio.

The docker has been tested on Linux (Ubuntu 14.04 and 16.04), macOS (10.11.6), and Windows (Windows 7 Enterprise). 

---
##### Installation of Docker

Ubuntu: follow [`the instructions`](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/) to get Docker CE for Ubuntu.


Mac: follow [`the instructions`](https://store.docker.com/editions/community/docker-ce-desktop-mac) to install [`the Stable verion of Docker CE`](https://download.docker.com/mac/stable/Docker.dmg) on Mac.

Windows: follow [`the instructions`](https://docs.docker.com/toolbox/toolbox_install_windows/) to install [`Docker Tookbox`](https://download.docker.com/win/stable/DockerToolbox.exe) on Windows.

---
To obtain the docker image and run the container,
```
[sudo] docker pull ucbd2k/mema
```
Ubuntu user may need to use `sudo` to run Docker.

A minimum of 4 GB memory is required to run the entire MEMA vignettes. Memmory allocation adjustment for Docker on Ubuntu is not needed as the default is "unlimited". On Mac and Windows it is done manually.

On Mac, click Docker whale icon in Launchpad or Applications folder to start Docker, then click Docker icon in top status bar and choose Preferences -> Advanced to increase Memory to 4.0 GB. 

On Windows, double-click Open Oracle VM VirtualBox icon on desktop, choose Settings -> System -> Motherboard to increase Base Memory to 4096 MB. 

```
[sudo] docker run -d -p <an available port>:8787 [-v <full path of a mount directory>:/opt] ucbd2k/mema
```
Optional argument `-v <full path of a mount directory>:/opt`: a directory can be mounted to a mount point (`/opt`, for instance) for file I/O in the mema docker. The mounted directory must be made readable and writable to the virtual RStudio. 

---
To run mema docker, open a browser and type in the address bar ``<Host URL>:<available port as specified>`` to start RStudio. Enter `rstudio` for both username and password.

Host URL on Ubuntu or Mac is `localhost`, if accessed locally. On Windows, the IP is shown when Docker is launched by double-clicking the Docker Quickstart Terminal icon on desktop, or it can be obtained from the output of `docker-machine ls` in the interactive shell window.

In the Synapse login step of the MEMA vignettes, supply your own login credential to `synapseLogin()`, since the `~/.synapseConfig` file does not exist for 'rstudio' user in the mema docker.

