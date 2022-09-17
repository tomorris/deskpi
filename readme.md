# Deskpi Super6C Raspberry Pi Cluster

## Intro
This is my project to set up a cluster of Raspberry Pi CM4s on a Deskpi Super6C board inspired by Jeff Geerling's work, including a similar cluster: [https://github.com/geerlingguy/deskpi-super6c-cluster](https://github.com/geerlingguy/deskpi-super6c-cluster).

After a couple of months closely watching [rpilocator](https://rpilocator.com/) I was finally able to fully populate the cluster with 6 CM4s. I'd prefer to have a matcihng set, but grabbed what I could to get up and running with a full set of six.

## Parts List
- Deskpi Super 6C board
- 6x RPI CM4:
	- 2x - CM4108000 (8GB ram, WiFi, no eMMC)
	- 2x - CM4002008 (2GB ram, no WiFi, 8Gb eMMC)
	- 2X - CM4101008 (1GB ram, Wifi, 8Gb eMMC)
- Mini-ITX Case (pretty basic one from Amazon)
- 6x CM4 heatsink kits
- 4x NVMe SSDs
- 2x 32GB Sandisk MicroSD (for the PIs without eMMC)

## Setup
After installing the CM4s and heat sinks, the RPIs were flashed with Raspberry Pi OS Lite (64-bit) using the instructions [here](https://www.raspberrypi.com/documentation/computers/compute-module.html#compute-module-4-2) and the Super6C's onboard microUSB connectors and a jumper on the "nRPIboot" position for each Pi.

Each Pi was named deskpi1.local, deskpi2.local, and so on for easy identificaiton.

After all the CM4s were set up, and the cluster conencted to my network, SSH connnection to each Pi was checked manually.

## Helpful Commands

`ansible all -m ping` - Ping all Pis using Ansible

`ansible all -B 500 -P 0 -a "shutdown now" -b` - Safely shutdown all Pis on the cluster

`ansible-playbook upgrade.yml` - Run upgrade playbook (currently update/upgrade Pi OS)
