# DHT

The DHT driver is implemented in software and works on all pins:

## Wiring

- Connect Vcc and GND to ESP32.
- Connect Data line to one Pin(eg. pin4).

![DHT](/static/sensor/dht.jpg)

## Code

```python
import dht
import machine

d = dht.DHT11(machine.Pin(4))
d.measure()
d.temperature() # eg. 23 (°C)
d.humidity()    # eg. 41 (% RH)

d = dht.DHT22(machine.Pin(4))
d.measure()
d.temperature() # eg. 23.6 (°C)
d.humidity()    # eg. 41.3 (% RH)
```
