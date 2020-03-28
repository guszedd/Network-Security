#  Network-Security
### JHU Network Security Homework #2

## Table of Contents
* Purpose and Architecture
* Readme
* Cloning this repository
* Server Runtime Setup
* Client Runtime Setup
* Notes

## Purpose and Architecture
This project demonstrates application level development on a Raspberry Pi using Docker containers and knowledge management using a GitHub Wiki. The runtime environment consisted of a client hosted on a Kali Linux virtual machine running a Kali Linux docker container. The client connects to a Kodi media server instance hosted by an Kali Server docker container running on a Raspberry Pi 4 with an Ubuntu server operating system.  Wiki markdown format documents were used for documentation and knowledge management.

The resulting architecture is depicted below:

![alt text](https://github.com/guszedd/Network-Security/blob/master/architecture2small.GIF "Architecture Diagram")


## Read me First
All "hosts" need to have the following prerequisites installed:
  * Docker - Chose the appropriate flavor of Docker for your requirements. EX `sudo apt-get install docker.io`
  * `net-tools`
  * `software-properties-common`
  * `systemd`
  * `systemd-sysv`
  * SSH client


## Cloning this repository
Ensure you have git installed (install and execute as root):
`# apt-get install git`

To clone this repository:

  1. `$ mkdir $HOME/kodi`
  2. `$ cd $HOME/kodi`
  3. `$ git clone https://github.com/guszedd/Network-Security.git`
  
 ## Server Runtime Setup
 Server setup instructions are located on the wiki: [Server Runtime Setup](https://github.com/guszedd/Network-Security/wiki/Server-Runtime-environment-instructions)

 ## Client Runtime Setup
 Client setup instructions are located on the wiki: [Client Runtime Setup](https://github.com/guszedd/Network-Security/wiki/Client-Runtime-environment-instructions)
 
 ## Notes
 * Adding media to Kodi requires following strict procedures as outlined on: https://kodi.wiki/view/Adding_video_sources 
  Steps include:
    * Preparing the Files: Naming & Folder Structures
    * Creating the Library: Adding Sources and Scrape (VERY IMPORTANT)
    * Modifying your Library
    * Safeguarding and Rebuilding
  If you do not have the right folder structure, add source, or scrape correctly your media will not appear on the client. You may just see the folder structure but not see the files. If that is the case, go back to the guide above and follow the instructions to Set Content and Scrape. Recommend using the default information provider for real movies.
  * This guide uses Universal Plug n Play (UPnP) for server support, however other options are available
  * Kodi relies on a graphical user interface (GUI) for setup and use. This requires X11 communication protocol or similar functionality.
  * This setup utilizes SSH -X user@IP in order to create an X11 connection between the remote host and the user's host. Ensure the user's host is capable of receiving and displaying this GUI information.
  * Do not infringe on copyrighted material
  
