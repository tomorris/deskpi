This is my project to set up a cluster of Raspberry Pi CM4s on a Deskpi Super6C board inspired by Jeff Geerling's work, including a similar cluster: [https://github.com/geerlingguy/deskpi-super6c-cluster](https://github.com/geerlingguy/deskpi-super6c-cluster).

After a couple of months closely watching [rpilocator](https://rpilocator.com/) I was finally able to fully populate the cluster with 6 CM4s.

Parts List:
- Deskpi Super 6C board
- 6x RPI CM4:
	- 2x - CM4 (8G ram, WiFi, no eMMC)
	- 2x - CM4 (2G ram, no WiFi, 8Gb eMMC)
	- 2X - CM4 (1G ram, Wifi, 8Gb eMMC)
- Mini-ITX Case (Amazon)
- 6x CM4 heatsink kits
- 4x SSDs
- 2x 32GB Sandisk MicroSD (for the PIs without eMMC)

After installing the CM4s and heat sinks, the RPIs were flashed with Raspberry Pi OS Lite (64-bit) using the instructions [here](https://www.raspberrypi.com/documentation/computers/compute-module.html#compute-module-4-2) and the Super6C's onboard microUSB connectors and a jumper on the "nRPIboot" position for each Pi.

