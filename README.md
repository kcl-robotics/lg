# Custom modify lgpio for ODI MLC

lgpio is a library for Linux Single Board Computers (SBC) which allows control of the General Purpose Input Outputs (GPIO).

## Download & Install

### Prerequisites

**MLC software should be installed before lgpio.**

A few packages are needed during installation of the Python modules.

* the SWIG code generator (to build lgpio.py from the C library)
* the Python development files (to build lgpio.py)
* the Python set up tools (to install lgpio.py and rgpio.py)

On Debian like systems these packages may be installed with the following commands.

- `sudo apt install swig python3-dev`
- `sudo apt install python3-setuptools`
- `echo "alias makelg='cd ~/lg; make; sudo make install; cp /usr/local/lib/python3.11/dist-packages/lgpio-0.2.2.0-py3.11-linux-aarch64.egg/_lgpio.cpython-311-aarch64-linux-gnu.so /home/user/ODI-MLC/venv/lib/python3.11/site-packages; cd ~/ODI-MLC'" >> ~/.bashrc`


### Download & Install

- `git clone git@github.com:kcl-robotics/lg.git`
- `makelg`

## GPIO

ALL GPIO are identified by their gpiochip line number.

## Features

* reading and writing GPIO singly and in groups
* software timed PWM and waves
* callbacks on GPIO level change
* notifications via pipe on GPIO level change
* I2C wrapper
* SPI wrapper
* serial link wrapper

* daemon interface
* access control (daemon interface)
* file handling (daemon interface)
* creating and running scripts (daemon interface)
* network access (daemon interface)

## Archive components

### The base library

* The lgpio C library to control local GPIO.

### The daemon

* The rgpiod daemon offers a socket interface to the lgpio library.
* The rgpio C library to control local and remote GPIO via the daemon.

### Python modules

* The lgpio Python module to control local GPIO.
* The rgpio Python module to control local and remote GPIO via the daemon.

### Utilities

* The rgs shell utility to control local and remote GPIO via the daemon.

## Documentation

See http://abyz.me.uk/lg/

## Example programs

See http://abyz.me.uk/lg/examples.html and the examples in the
EXAMPLES directory.
