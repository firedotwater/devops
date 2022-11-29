# What the quark is M5-Stack :question:

The [M5-Stack](https://m5stack.com) is a fancy and nice IoT Developer Module, with an ESP32 core processore. It contains a lot of compatible modules and several units. And the best part is, it is mostly everythin open source. It has apparantly a **huge** community which will help you out.

## Our exercises :muscle:

We have got our own exercises from Armin and Marcello. 

### Exercise Nr. 0


In the first Exercise we had to get along with the M5Stack itself. We had to "configure" the M5 and add the API key from the M5 to the online enviroment. After adding the key we could start to play around with the enviroment itself and the M5.

### Exercise Nr. 1

In this exercises we had to do these things with the acceleration from the M5 Stack:

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

### Exercise Nr. 2

The second Exercise was something similiar like the previous one. I had to work with the accelleration and beschleinigung:

```
from m5stack import *
from m5ui import *
from uiflow import *
from flow import ezdata
import wifiCfg
import time
import imu
remoteInit()

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

lcd.qrcode('https://flow.m5stack.com/remote?id=undefined', 72, 60, 150)
while True:
  beschleinigung = math.sqrt(square(imu0.acceleration[0]) + square(imu0.acceleration[1]) + square(imu0.acceleration[2]))
  lbBeschleunigung.setText(str(beschleinigung))
  ezdata.addToList('WzkpqZwmeXUfMDYqDNHPs6Zy6Hohwmne', 'beschleunigung', ({'timestamp':(ezdata.getCurrentISODateTime()),'acceleration':beschleinigung}))
  wait(1)
  wait_ms(2)
```

### Exercise Nr. 3

In thos exercise I have played around with the AWS subscription with the M5. I have created a free tier account on AWS and made the requiered adjustment and settings.

Here is the needed code:

```
from m5stack import *
from m5ui import *
from uiflow import *
from IoTcloud.AWS import AWS
import wifiCfg
import time

setScreenColor(0x222222)

label0 = M5TextBox(83, 106, "No Message yet", lcd.FONT_Default, 0xFFFFFF, rotate=0)
label1 = M5TextBox(83, 67, "Message is:", lcd.FONT_Default, 0xFFFFFF, rotate=0)

def fun_m5stack_core_bla_(topic_data):
  # global params
  label1.setText('Message arrived')
  label0.setText(str((str('Message is:') + str(topic_data))))
  pass

wifiCfg.autoConnect(lcdShow=False)
while not (wifiCfg.wlan_sta.isconnected()):
  wait(1)
aws = AWS(things_name='m5stack_fabio', host='a1los3338lpcll-ats.iot.eu-central-1.amazonaws.com', port=8883, keepalive=60, cert_file_path="/flash/res/aws-certificate.pem.crt", private_key_path="/flash/res/aws-private.pem.key")
aws.subscribe(str('m5stack/core/bla'), fun_m5stack_core_bla_)
aws.start()
```

### Exercise Nr. 4

This exercise continues from the exercise 3 and goes on with the AWS service.


Here is the code

```
from m5stack import *
from m5ui import *
from uiflow import *
from m5mqtt import M5mqtt
import time

setScreenColor(0x222222)

def buttonA_wasPressed():
  # global params
  m5mqtt.publish(str('bntApressed'), str(''), 0)
  pass
btnA.wasPressed(buttonA_wasPressed)

m5mqtt = M5mqtt('M5Fire', '3.71.14.93', 1883, '', '', 300)
m5mqtt.start()
while True:
  wait(4)
  m5mqtt.publish(str('M5Output'), str('Hello World'), 0)
  wait_ms(2)
```
