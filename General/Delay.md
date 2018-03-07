# Delay

Just like other boards, MicroPython also has functions to delay itself for a while.

```python
import time

time.sleep(1)           # sleep for 1 second
time.sleep_ms(500)      # sleep for 500 milliseconds
time.sleep_us(10)       # sleep for 10 microseconds
start = time.ticks_ms() # get millisecond counter
delta = time.ticks_diff(time.ticks_ms(), start) # compute time difference
```

If we have a LED connected to pin 0, then type in the following code and the LED will blink for several times.

```python
import time
from machine import Pin

p0 = Pin(0, Pin.OUT)
state = 0
for i in range(0, 15):
    p0.value(state)
    state = 1 - state
    time.sleep(1)
```
