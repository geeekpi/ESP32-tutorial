# Buzzer

A buzzer is a component used to generate a sound and it's simple to use just like a GPIO.  
Give high level and it will make a sound.

## Wiring

- Connect - pin to ESP32's GND.
- Connect + pin to pin 4.

![buzzer](/static/GPIO/buzzer.jpg)

## Code

```python
import machine

p = machine.Pin(4, machine.Pin.OUT)
```

Use `p.value(1)` to make a sound or `p.value(0)` to get the silence.

