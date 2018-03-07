# Linux

## Connecting 

To connect ESP32 on Linux such as Ubuntu, we need the same tool as that on MacOS, picocom.

On Ubuntu, you can install the tool using the below command.

```
sudo apt-get install picocom
```

### picocom

Open a terminal and find your ESP32's serial num by `ls /dev/` which may be like `/dev/ttyUSB0`.

Use the command to connect ESP32.

```
sudo picocom -b 115200 /dev/ttyUSB0
```

If you see the terminal like below, then you can move on to the next steps.

![linux serial](/static/Installation/linux_repl.png)

