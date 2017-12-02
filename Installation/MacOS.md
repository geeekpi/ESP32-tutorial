# Mac OS

## Flashing

We use esptool to flash the firmware.

```bash
pip install esptool
```

### How to use

#### Erase Former Firmware

```bash
sudo esptool.py --chip esp32 --port /dev/tty.SLAB_USBtoUART erase_flash
```

You may see things like this.

```
esptool.py v2.1
Connecting........_____...
Chip is ESP32D0WDQ6 (revision 0)
Uploading stub...
Running stub...
Stub running...
Erasing flash (this may take a while)...
Chip erase completed successfully in 3.2s
Hard resetting...
```

##### Confirm the Port
If you can't ensure which one to write, do the steps as following to confirm the Port.

- Unplug the board and run `ls /dev/` in the terminal.
- Plug in the board with Mac and run the command again.
- Compare two outputs and you'll find the port.

#### Flash the New Firmware

```bash
sudo esptool.py --chip esp32 --port /dev/tty.SLAB_USBtoUART write_flash -z 0x1000 ~/Downloads/esp32.bin
```

You may see things like this.

```
esptool.py v2.1
Connecting........_
Chip is ESP32D0WDQ6 (revision 0)
Uploading stub...
Running stub...
Stub running...
Configuring flash size...
Auto-detected Flash size: 4MB
Compressed 936288 bytes to 587495...
Wrote 936288 bytes (587495 compressed) at 0x00001000 in 51.7 seconds (effective 144.8 kbit/s)...
Hash of data verified.

Leaving...
Hard resetting...
```

If you get something wrong here, maybe you should erase the former firmware and try to flash it again.

## Connecting

To connect ESP32, we need a tool to open a Serial and we choose picocom on Mac OS.

```bash
brew install picocom
```

### How to use

```bash
sudo picocom -b 115200 /dev/tty.SLAB_USBtoUART
```

You may see things like this.

```
picocom v2.2

port is        : /dev/tty.SLAB_USBtoUART
flowcontrol    : none
baudrate is    : 115200
parity is      : none
databits are   : 8
stopbits are   : 1
escape is      : C-a
local echo is  : no
noinit is      : no
noreset is     : no
nolock is      : no
send_cmd is    : sz -vv
receive_cmd is : rz -vv -E
imap is        :
omap is        :
emap is        : crcrlf,delbs,

Type [C-a] [C-h] to see available commands

Terminal ready

>>>
```

Now you're in the MicroPython REPL and ready to begin with ESP32.
