# Debian-ReadyNas-RNDP4000v2

Documenting my procedure for installing latest Debian (Bullseye) on the NetGear ReadyNAS NV+ v2

#Resouces: 
1. http://git.natisbad.org/NAS/index.html#debinstall
2. https://senpai.club/upgrade-readynas-duo-v2-to-latest-debian/index.html
3. https://ftp.debian.org/debian/dists/buster/main/installer-armel/current/images/kirkwood/netboot/marvell/guruplug/
4. https://ftp.debian.org/debian/dists/bullseye/main/installer-armel/current/images/kirkwood/netboot/marvell/guruplug/

I couldn't get the USB instructions (2) to work, so I used tftpboot:

setenv serverip 192.168.0.165

setenv ipaddr 192.168.0.199

setenv gatewayip 192.168.0.1

tftpboot 1200000 uImage

tftpboot 2000000 uInitrd

set bootargs console=ttyS0,115200 earlyprintk

bootm 0x1200000 0x2000000

Now the debian installer should start
