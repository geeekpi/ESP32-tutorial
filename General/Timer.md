# Timer

Virtual (RTOS-based) timers are supported. Use the machine.Timer class with timer ID of -1:

```python
from machine import Timer

tim = Timer(-1)
tim.init(period=5000, mode=Timer.ONE_SHOT, callback=lambda t:print(1))
tim.init(period=2000, mode=Timer.PERIODIC, callback=lambda t:print(2))
```

We use a `lambda` function as a callback, but actually normal functions can also be used as callback here.

```python
from machine import Timer
from machine import Pin

def blink():
  if p4.value()==1:
    p4.value(0)
  else:
    p4.value(1)

p4 = Pin(4, Pin.OUT)
tim = Timer(-1)
tim.init(period=5000, mode=Timer.PERIODIC, callback=blink)
```

Connect a LED to pin 4, it is another way to perform BLINK.

