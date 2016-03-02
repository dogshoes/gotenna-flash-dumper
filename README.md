## Overview

This program will allow you to dump the flash chip on a [goTenna](http://www.gotenna.com/) connected to your computer.  The flash contains the firmware, diagnostic log, configuration, and message queue.

Requires Python 2.7.5+ and [pyserial 2](https://pypi.python.org/pypi/pyserial).  Tested on Fedora 20, and will likely work fine on most any Linux distribution.

Tested against goTenna firmware 00.18.02, 00.21.04, and 0.23.2.  All firmware versions work great.

## Connect your goTenna

Connect your goTenna to your computer over USB and extend the antenna to turn it on.  It will expose a USB serial port.  Figure out what serial device it's exposing on your computer.

```ShellSession
[jhe@oxcart ~]$ dmesg | grep goTenna -a5
[43446.128944] usb 2-2.1: new full-speed USB device number 20 using uhci_hcd
[43446.234635] usb 2-2.1: New USB device found, idVendor=1fc9, idProduct=2047
[43446.234643] usb 2-2.1: New USB device strings: Mfr=1, Product=2, SerialNumber=3
[43446.234647] usb 2-2.1: Product: goTenna
[43446.234656] usb 2-2.1: Manufacturer: goTenna, Inc
[43446.234659] usb 2-2.1: SerialNumber: 123456789ABCDEF
[43446.242217] cdc_acm 2-2.1:1.0: ttyACM0: USB ACM device
```

## Dump the flash

Use the `dump-gotenna-flash` program to instruct the goTenna to output the flash contents over the serial port.  The program achieves this by issuing the `read_eflash` goTenna cli command.  You'll end up with a cli session log containing the contents of the flash, along with several other diagnostic messages.

The version reported may be different than you're expecting as the version displayed in the CLI and the app differ.

```ShellSession
[jhe@oxcart gotenna-flash-dumper]$ sudo ./dump-gotenna-flash /dev/ttyACM0 flash.log
Connected to serial port /dev/ttyACM0.
Waiting for idle on the goTenna... Please wait 5 seconds.
Found goTenna running firmware 00.15.04.
The goTenna is available and ready.  Sit back and relax, this will take a bit of time.
Dumping flash.  Do not disconnect or turn the goTenna off!
Saving: 100.00%
Flash read in 0:21:59.210511.
```

## Convert the flash log to a binary

Next, use the `flash-log-to-binary` program to parse the flash log and output a binary flash file which can then be inspected and/or disassembled.

```ShellSession
[jhe@oxcart gotenna-flash-dumper]$ ./flash-log-to-binary flash.log flash.bin 
```
