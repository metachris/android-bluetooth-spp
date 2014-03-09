android-bluetooth-spp
=====================

Bluetooth Serial Communication with Android + PC/Arduino


How to run Bluetooth Chat between Android and PC
------------------------------------------------

$ apt-get install libbluetooth-dev
$ pip install pybluez

* Pair computer and Android phone
* Find Android hw addr.:

	$ hcitool scan

* Create a serial channel on the PC: 

	$ sudo sdptool add --channel=3 SP

* Bind Android BT hw addr. to rfcomm0 on our SPP channel: 

	$ sudo rfcomm bind rfcomm0 B0:EC:71:CF:5B:97 3

* Start python bluetooth chat SPP server:

	$ python src/python-spp-server/bluetooth_chat.py
