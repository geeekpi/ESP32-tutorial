# Relay

A relay is a component used to control higher voltage or current by lower ones. It's just like a simple GPIO while writing code.

Give high level and the controlled circuit will be closed.

## Wiring

- Put the relay in a circuit.
- Connect GND and VCC to ESP32.
- Connect IN pin to Pin4.

![relay](/static/GPIO/relay.jpg)

## Code

```python
import machine

p = machine.Pin(4, machine.Pin.OUT)
```

Then use `p.value(1)` to close the relay circuit and the led will be lighted. Use `p.value(0)` and the led will be off.
