# check_lustre
Updated Fork of Josh Malone's (@48kRAM) on Nagios' plugin

* Added new path to health_check into script.
* Future: check inode usage


# Original Read Me:

Simple check plugin to monitor the health and filesystem size of one or more lustre filesystems. This check must be run on a system that mounts the monitored lustre filesystems. Uses 'lfs df' to gather info on filesystems so it should not use any costly (in terms of performance) commands. Outputs performance data for filesystem size graphing. Graphs both utilization and space used.
This is a simple check plugin to monitor the health and filesystem size of one or more lustre filesystems. This check must be run on a system that mounts the monitored lustre filesystems. Use NRPE to execute it as a remote check.

This plugin uses lfs df to gather info on filesystems so it should not use any costly (in terms of performance) commands like ls, etc. In addition, it also outputs performance data so you can get pretty graphs of filesystem size (bytes) and utilization (percent). Now uses an alarm to detect if the 'lfs' call is hanging.

Rev 3: Warning and Critical space thresholds now implemented.
Rev 3: Added '-t' option to ignore OSTs that are temporarily unavailable (such as IDs reserved for future use)

You must have nagios-plugins installed on the lustre host as this plugin requires utils.pm.

This is an early release of this plugin (since I can't find any other on this site) but it has shown to be stable and helpful in our environment. This plugin has been minimally tested at this point; if your output of lfs df is different somehow you may receive false alarms.

This plugin has been tested on lustre 1.8.9 and 2.3.0 using perl 5.8 and perl 5.12.

Future improvements: check inode usage as well as space.
