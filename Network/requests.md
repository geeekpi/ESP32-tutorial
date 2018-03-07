# requests

On MicroPython we also have a customized requests module similar to the original requests.

It's called `urequests`. After you connect a WiFi, you can try the code below.

```python
import urequests

r = urequests.get('http://www.baidu.com')
r.text
```

It will return the HTML code of the website. If the response is in json or some other format, the module has other methods to resolve it.

![baidu response](/static/Network/baidu_response.png)

