# Description: runtime environment for container on kali
# Usage info goes here  -- add words ---

# setup the image to use
FROM kalilinux/kali-rolling

# have to set to non-interactive so it doesn't try to get user input
ENV DEBIAN_FRONTEND noninteractive

# setup environment for systemd
ENV container docker

# update upgrade
RUN apt-get update
RUN apt-get upgrade -y

# install some useful tools
RUN apt-get install sudo iputils-ping net-tools nano vim git-core -y
RUN apt-get install software-properties-common -y
RUN apt-get install systemd systemd-sysv -y

# setup ssh / x11 depend
RUN apt-get install openssh-server -y
# RUN systemctl start ssh.service #can't do this -- this is an image
RUN apt-get install --no-install-recommends xorg lxdm lxqt -y

# set root password
RUN echo "root:toor" | chpasswd

# ssh setting
RUN echo "PermitRootLogin yes" >> /etc/ssh/sshd_config
RUN echo "PasswordAuthentication yes" >> /etc/ssh/sshd_config
ENTRYPOINT service ssh start && bash

# let's send some useful information to the user at this point
RUN echo 'note can only have ssh running on the container, not in VM'
RUN echo 'to use this container, from your VM (host) run: ssh -X clientuser@ipaddrofrpi'
RUN echo 'once you are in the SSH session then type: kodi'
RUN echo 'Kodi should open and you can now configure the software accordingly'

# Things to verify
# can we create our own user or does it have to be "pi" or one of the root users?
# does this even work
