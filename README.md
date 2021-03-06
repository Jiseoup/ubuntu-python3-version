# INSTALL and SELECT python3 version in Ubuntu 18.04
This document introducing how to *install* and *select* **`python3`** version in **`ubuntu 18.04`**.

## CHECK CURRENT VERSION
```bash
$ python3 --version
```
### Example Output
```bash
Python 3.6.9
```

## INSTALL WITH PACKAGE MANAGER
```bash
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get install python3.7
$ sudo apt-get install python3.8
```

### Install Python 3.10 Version
**`python3.10`** version is not available in **`ubuntu 18.04`**'s default repositories. So, the python package should be added through an additional repository. We use the repository of [deadsnakes](https://github.com/deadsnakes). If you want to install **`python3.10`** version as well, follow the command below.
```bash
$ sudo apt-get install software-properties-common
$ sudo add-apt-repository ppa:deadsnakes/ppa
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get install python3.10
```

## VERSION SETTINGS
You can define the priority level as you like, the higher level, the higher priority.
```c
// Set 3.6 version as priority level 1
$ sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.6 1

// Set 3.7 version as priority level 2
$ sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.7 2

// Set 3.8 version as priority level 3
$ sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.8 3

// Set 3.10 version as priority level 4 (Use this command only if you have installed python 3.10 version.)
$ sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.10 4
```

## SELECT VERSION
You can change the version using the command below.
```bash
$ sudo update-alternatives --config python3
```
<img src="/img/select_version.png"/>

* You can change the version by entering a number.
* Auto mode uses the highest priority version. -> **`python3.8`**

If you want to return to auto mode, using the command below.
```bash
$ sudo update-alternatives --auto python3
```
## CAUTION !
If you want to use command **`$ sudo apt-get update`**, please use **`python3.6`**, the default version of the **`ubuntu 18.04`** system.
