# ADC

ADC is available on a dedicated pin. Note that input voltages on the ADC pin must be between 0v and 1.0v.

Use the `machine.ADC` class:

```python
from machine import ADC
from machine import Pin

adc = ADC(Pin(32))            # create ADC object on ADC pin(available for pin32 to pin35)
adc.read()              # read value, 0-4096
```

## Potentiometer
A potentiometer is a simple knob that provides a variable resistance, and we use it to show you how the ADC class works.

### Wiring

- Connect side pins to GND pin and 3.3V pin.
- Connect middle pin to pin32.

![Potentiometer](/static/ADC/potentiometer.JPG)

### Code

```python
from machine import ADC
from machine import Pin

adc = ADC(Pin(32))

while True:
	print adc.read()
```

As you rotate the potentiometer, the value printed will change at the same time between 0 and 4096.
