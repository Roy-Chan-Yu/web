## Filesystem Hierarchy Standard (FHS)

|Directory type  |Types of files stored    |
|----------------|------------------------|
|`Binary directories`  |Contains binary or compiled source code files, eg, /bin, /sbin, etc.  |
|`Configuration directories`  |Contains `configuration files of the system`, eg, /etc, /boot.   |
|`Data directories`    |Stores data files, eg, `/home, /root`, etc.    |
|`Memory directories`  |Stores device files which doesn't take up actual hard disk space, eg, `/dev, /proc, /sys`.|
|`Usr (Unix System Resources)`|Contains sharable, read only data, eg, `/usr/bin, /usr/lib,` etc.   |
|var (variable directory)   |`Contains larger size data`, eg, /var/log, /var/cache, etc.      |
|Non-standard directories   |Directories which do not come under standard FHS, eg, `lost+found, /run, etc`.     |


## /bin

- user binaries, executable files, Linux commands that are used in single user mode
- i.e.like cat, cp, cd, ls

## /lib
- The '/lib' directory contains shared libraries

## Configuration Directory

## /boot
- contains `boot loader files` which are essential to boot the system

## /etc
- Almost everything `related to the configuration of your system is placed here`. 

## /etc/init.d
- The term 'init' is short for initialization. This directory contains script to `control the system or to start and stop the daemons `(background process). <font color="red">The init is a daemon process</font> that `continues running until the system is shut down`.

## Unix System Resources (/usr)

- only contains shareable read-only data.