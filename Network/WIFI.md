# WIFI

The network module have several methods:

```python
import network

wlan = network.WLAN(network.STA_IF) # create station interface
wlan.active(True)       # activate the interface
wlan.scan()             # scan for access points
wlan.isconnected()      # check if the station is connected to an AP
wlan.connect('essid', 'password') # connect to an AP
wlan.config('mac')      # get the interface's MAC adddress
wlan.ifconfig()         # get the interface's IP/netmask/gw/DNS addresses

ap = network.WLAN(network.AP_IF) # create access-point interface
ap.active(True)         # activate the interface
ap.config(essid='ESP-AP') # set the ESSID of the access point
```

A typical process to connect a WiFi may be like below, and after that you can connect a server or some websites.

```python
import network

wlan = network.WLAN(network.STA_IF)
wlan.active(True)       # activate the interface
wlan.connect('essid', 'password') # connect to an AP
```
