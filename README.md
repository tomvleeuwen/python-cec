# python-cec - libcec bindings for Python

*python-cec* allows you to control your TV, reciever and other CEC-compliant HDMI devices from a python script on a computer. Most computer graphics cards don't support CEC; you'll need a [http://www.pulse-eight.com/store/products/104-usb-hdmi-cec-adapter.aspx](Pulse-Eight USB-CEC adapter) or a Raspberry Pi (Untested).

## Installing:

### Install dependencies
To build python-cec, you need the libcec development libraries:

On Gentoo:
```
sudo emerge libcec
```

On Ubuntu:
```
sudo apt-get install libcec-dev
```

### Checkout, build and install

```
git clone https://github.com/trainman419/python-cec.git
cd python-cec
python setup.py install
```

## Getting Started

A simple example to turn your TV on:

```
import cec

cec.open()

tv = cec.Device(0)
tv.power_on()
```

## API


```
import cec

adapters = cec.list_adapters()

cec.open( adapter = cec.DEFAULT )

cec.close() // not implemented yet

cec.add_callback( event, handler ) // not implemented yet

cec.remove_callback( event, handler ) // not implemented yet

devices = cec.list_devices()

class Device:
   is_on()
   power_on()
   standby()
   address
   physical_address
   vendor
   osd_string // not implemented yet
   cec_version // not implemented yet
   language // not implemented yet
   #TODO: get volume
   #TODO: get active input

cec.set_active_source() // not implemented yet
cec.set_inactive_source() // not implemented yet

cec.volume_up()
cec.volume_down()

# TODO: set physical address
```
