# M5 Stack

Here are some of the different Exercises from the M5 Stack.

## Exercise's
### Exercise Nr. 0


In the first Exercise we had to get along with the M5Stack itself. We had to "configure" the M5 and add the API key from the M5 to the online enviroment. After adding the key we could start to play around with the enviroment itself and the M5.


### Exercise Nr. 1

In this exercises we had to do these things

```
from m5stack import *
from m5ui import *
from uiflow import *
from flow import ezdata
import wifiCfg
import time
import imu


setScreenColor(0x222222)


x = None
beschleinigung = None

wifiCfg.autoConnect(lcdShow=False)
imu0 = imu.IMU()

lbBeschleunigung = M5TextBox(147, 81, "label0", lcd.FONT_Default, 0xFFFFFF, rotate=0)

import math


# Describe this function...
def square(x):
  global beschleinigung
  return x * x



while True:
  beschleinigung = math.sqrt(square(imu0.acceleration[0]) + square(imu0.acceleration[1]))
  lbBeschleunigung.setText(str(beschleinigung))
  ezdata.setData('WzkpqZwmeXUfMDYqDNHPs6Zy6Hohwmne', 'accelleration', beschleinigung)
  wait(1)
  wait_ms(2)
```
