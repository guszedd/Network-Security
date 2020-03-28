#  Network-Security
## Network Security Homework #2

## Table of Contents
* Readme
* Cloning this repository
* Server Runtime Setup
* Client Runtime Setup
* Notes

![alt text](https://github.com/guszedd/Network-Security/blob/master/jhu2020.jpg "Logo Title Text 1")

## Read me First
This project demonstrates application level development on a Raspberry Pi using Docker containers, cross-compilation, and knowledge management using a GitHub Wiki. In this project the intent was to setup a runtime environment and a build environment. The runtime environment consisted of a client hosted on a Kali Linux virtual machine running a Kali Linux docker container. The client connects to a Kodi media server instance hosted by an Ubuntu Server docker container running on a Raspberry Pi 4 with an Ubuntu server operating system. The build environment allowed developers to build the applications on an x86-64 bit architecture but cross compile it for an ARM64 bit architecture. Wiki markdown format documents were used for documentation and knowledge management.

The resulting architecture is depicted below:



## Cloning this repository
Ensure you have git installed (install and execute as root):
`# apt-get install git`

To clone this repository:

  1. `$ mkdir $HOME/kodi`
  2. `$ cd $HOME/kodi`
  3. `$ git clone https://github.com/guszedd/Network-Security.git`
  
 ## Server Runtime Setup
 The instructions here setup kodi in the server target (Docker container on Kali).
Follow the below:

```
$ mkdir $HOME/kodi
$ cd $HOME/kodi
$ git clone https://github.com/guszedd/Network-Security.git
$ cd Network-Security/dockerfile_server
$ sudo docker build --network host --tag kodi_server_img .
$ sudo docker run -it --name kodi_server --privileged -v /sys/fs/cgroup:/sys/fs/cgroup:ro --network host kodi_server_img
```

than check ip address with `ifconfig` - this example consider container'sip address is `192.168.232.132`.

on the RPI run ` $ ssh -X root@192.168.232.132 `
the password of root is `toor`
and then run `$ kodi`

 
 
 ## Client Runtime Setup
 
 
 
 ## Notes
