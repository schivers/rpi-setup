## Set up IP addressing on RPi

This repo contains info on asetting up the RPi IP Addressing

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- To be updated

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Install Raspbian using Pi Imager

## IP Addressing

### Using dhcpcd

Before you begin with the assignment of a private IP address for Raspberry Pi, check whether DHCPCD is already activated using the following command:

```
sudo service dhcpcd status
```

In case it’s not, activate DHCPCD as follows:

```sudo service dhcpcd start
sudo systemctl enable dhcpcd
```

Now make sure that the configuration of the file /etc/network/interfaceshas the original status. For this, the ‘iface’ configuration needs to be set at ‘manual’ for the interfaces.

For the editing of the activated DHCPCDs, start by opening the configuration file /etc/dhcpcd.confand running the following command:

```
sudo nano /etc/dhcpcd.conf
```

Edit to reflect ..

```
interface eth0
static ip_address=192.168.0.4/24
static routers=192.168.0.1
static domain_name_servers=192.168.0.1
```

Now reload the Pi
```
sudo reboot
```

done.
