munin-pcsensor
==============

Creates Munin graphs from the data delivered from an attached TEMPer USB Thermometer.
For data collection the `pcsensor` utility is needed (by default it resides in */usr/local/bin/*), it can be obtained in source or binary form from different places like [here](https://github.com/jeroensteenhuis/pcsensor).
Script was tested with pcsensor version 1.0.1.

Install
-------

Clone this repository or download the pcsensor file and create a
symlink as *root* in /etc/munin/plugins by using e.g.:

	cd /etc/munin/plugins; ln -s /path/to/pcsensor

**Don't forget to restart your munin-node deamon.**
