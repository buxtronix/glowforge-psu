# HV driver board

This contains a work-in-progress reverse-engineered schematic of the HV driver
daughterboard. This is the "HV Supervisor" show in
[this post](https://community.openglow.org/t/reverse-engineering-pr0n/242/2).

The SOT23-5 chips are likely opamps or comparators, possibly LMC7101 or TLV7211.

The main chip, an [LT6599ATD](https://www.st.com/resource/en/datasheet/l6599.pdf)
is a fairly common switchmode controller.

![Driver board](../images/gf-psu-top.jpg)

