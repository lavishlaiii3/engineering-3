## CircuitPython 
This repository will actually serve as an aid to help you get started with your own template.  You should copy the raw form of this readme into your own, and use this template to write your own.  If you want to draw inspiration from other classmates, feel free to check [this directory of all students!](https://github.com/chssigma/Class_Accounts).
## Table of Contents
* [Table of Contents](#TableOfContents)
* [Hello_CircuitPython](#Hello_Circuimport time)
* [CircuitPython_Servo](#CircuitPython_Servo)
* [CircuitPython_LCD](#CircuitPython_LCD)
* [NextAssignmentGoesHere](#NextAssignment)
---

## Motor control

### Description & Code Snippets
As I moved my potentiometer it increased the speed of the motor. 

 
```python
import board
import analog

motor=analogio.AnalogOut(board.A0)
pot=analogio.AnalogIn(board.A1)
while True:
    speed=pot.value
    motor.value=speed

```

**Lastly, please end this section with a link to your code or file.**  

### Evidence
![WIN_20230926_14_32_28_Pro](https://github.com/lavishlaiii3/engineering-3/assets/143545115/8339bf38-414c-42e2-92a4-2ce4e4e31e71)



### Wiring


![WIN_20230926_15_31_36_Pro](https://github.com/lavishlaiii3/engineering-3/assets/143545115/35f29aea-3d34-4458-bfe0-478893cd179f)

### Reflection
This assignment on Canvas was pretty self-explanatory. I just forgot how to wire my Potentiometer. To solve this problem I looked at my old notebook from last year. For wiring, I also got confused with multiple wires having to go to the same pin so I created multiply 5v and gnd.



## CircuitPython Servo

### Description & Code Snippets
The goal was to wire a 180 servo and get it to rotate back and forth between 0 and 180 degrees by using a button using 2 different buttons. To accomplish we used the 3 wires for ground, power, and signal. 


```python
# SPDX-FileCopyrightText: 2018 Kattni Rembor for Adafruit Industries
#
# SPDX-License-Identifier: MIT

"""CircuitPython Essentials Capacitive Touch on two pins example. Does not work on Trinket M0!"""
import time
import board
import touchio
import pwmio
from adafruit_motor import servo

# create a PWMOut object on Pin A2.
pwm = pwmio.PWMOut(board.A2, duty_cycle=2 ** 15, frequency=50)

# Create a servo object, my_servo.
my_servo = servo.ContinuousServo(pwm)

touch_A4 = touchio.TouchIn(board.A4)  # Not a touch pin on Trinket M0!
touch_A5 = touchio.TouchIn(board.A5)  # Not a touch pin on Trinket M0!

while True:
    my_servo.throttle = 0.0
    while touch_A4.value:
        my_servo.throttle = 1.0
        time.sleep(.5)
    while touch_A5.value:
        my_servo.throttle = -1.0
        time.sleep(.5)

```



### Evidence


https://github.com/lavishlaiii3/engineering-3/assets/143545115/8e7118c7-7450-4285-a2f4-745ef5a488a4





### Wiring
![image](https://github.com/lavishlaiii3/engineering-3/assets/143545115/5506b60b-1c62-4211-8107-9bf3487e7f09)


### Reflection
This wasn't too challenging it was a review from last year. What was challenging was coding since using a new app so I looked online and got help from my peers. 

## distance sensor
### Description & Code Snippets
The goal of this assignment was to  shift the color of a neopixel based on the distance from an ultrasonic sensor.
 
```python
# SPDX-FileCopyrightText: 2021 ladyada for Adafruit Industries
# SPDX-License-Identifier: MIT

import time
import board
import adafruit_hcsr04
import neopixel
import simpleio

NUMPIXELS = 1  # Update this to match the number of LEDs.
SPEED = 0.1  # Increase to slow down the rainbow. Decrease to speed it up.
BRIGHTNESS = 0.2  # A number between 0.0 and 1.0, where 0.0 is off, and 1.0 is max.
PIN = board.NEOPIXEL  # This is the default pin on the 5x5 NeoPixel Grid BFF.

pixels = neopixel.NeoPixel(PIN, NUMPIXELS, brightness=BRIGHTNESS, auto_write=False)
sonar = adafruit_hcsr04.HCSR04(trigger_pin=board.D5, echo_pin=board.D6)
RED = (255, 0, 0)
GREEN = (0, 255, 0)
BLUE = (0, 0, 255)

while True:
    try:
        print((sonar.distance))
        time.sleep(0.1)
        if (sonar.distance < 5):
            pixels.fill(RED)
            pixels.show()
            time.sleep(0.1)
        elif (5 < sonar.distance < 20):
            x = simpleio.map_range((sonar.distance),5,20,0,255)
            pixels.fill((255-x, 0, x))
            pixels.show()
            time.sleep(0.1)
        elif (sonar.distance == 20):
            pixels.fill(BLUE)
            pixels.show()
            time.sleep(0.1)
        elif (20 < sonar.distance < 35):
            x = simpleio.map_range((sonar.distance),20,35,0,255)
            pixels.fill((0, x, 255-x))
            pixels.show()
            time.sleep(0.1)
        elif (sonar.distance > 35):
            pixels.fill(GREEN)
            pixels.show()
            time.sleep(0.1)
    except RuntimeError:
        print("Retrying!")


```

**Lastly, please end this section with a link to your code or file.**  

### Evidence 
![unnamedv](https://github.com/lavishlaiii3/engineering-3/assets/143545115/977d09db-040d-4428-86ac-0e88c39d501f)


### Wiring
![image](https://github.com/lavishlaiii3/engineering-3/assets/143545115/118dc44d-6f85-4659-829e-2050213049c6)

### Reflection
This wiring wasn't bad because I used my old notebook from last year. It helped me get to know how to work the coding thing more since I got the wiring done in a good timely matter. I did run into some diffcuilts with my code that I didn't understand but my peers helped me.


## Onshape hanger

### Assignment Description

The goal for this assignment was to create a hanger using certain measurements to get the correct mass. 
### Evidence

![Capture](https://github.com/lavishlaiii3/engineering-3/assets/143545115/06007277-fcdc-4f5c-a720-529b57472872)
![eng](https://github.com/lavishlaiii3/engineering-3/assets/143545115/cbd8bc42-c669-4373-841d-e65cf035c37c)


### Part Link 
https://cvilleschools.onshape.com/documents/b1d132e7e0424f9d639298aa/w/2d240396e6e3b38146958e59/e/0d087c803922b2328f0815bf?renderMode=0&uiState=651c60a2d82c8215c1b3e5da

### Reflection

Something that went well was the understanding of the measurement and me and Korine's collaboration. Also remebering little shortcuts from last year. Something that went bad was mirroring because when it was to mirror My plan wouldn't show so mr. miller showed me how to make a plane.
&nbsp;

 
## Onshape swing arm

### Assignment Description
For this assignment, we were getting comfortable using dimesons and using the last 4 slides to help create the part. Mostly it was to get ready to earn your  Certified Onshape Associate certification.
### Evidence

![swing](https://github.com/lavishlaiii3/engineering-3/assets/143545115/b456129c-fed3-4a16-83f4-40b944983c5e)
![swing3](https://github.com/lavishlaiii3/engineering-3/assets/143545115/4ec02fd9-569e-4639-be5a-f2770a80d3a3)

![swing2](https://github.com/lavishlaiii3/engineering-3/assets/143545115/abc7f67a-4021-4727-912e-1adfb92d64e3)

### Part Link 
https://cvilleschools.onshape.com/documents/dda6d6d0e8e82c1ed3f6dfcc/w/8f824fb39a93bdf344b566c0/e/04694da48d226dd21f72e0cf?renderMode=0&uiState=653959c3155aa40d03e3be7d
### Reflection

This assignment was difficult because I didn't know where to start. But getting help from Mr. Miller ended up doing each section separately and actually using the instructions. This made me feel more confident in onshape because it was something out of a comfort zone. 




## Multipart Design Practice

### Assignment Description

For this assignment, we had to use  drawings to help us create a multi-part cylinder with variables for different configurations. At the end of the assignment, we had to take a quiz about the mass.


### Evidence
![Capture](https://github.com/lavishlaiii3/engineering-3/assets/143545115/8b9976f7-21c0-40ce-b2f6-0d393ae655b1)
![Capture2](https://github.com/lavishlaiii3/engineering-3/assets/143545115/6b0b9187-550f-4aac-8127-474c49f6fc7f)

![Capture3](https://github.com/lavishlaiii3/engineering-3/assets/143545115/c8de1011-0c51-4065-8ae1-1f9f5f70e77a)


### Part Link 
https://cvilleschools.onshape.com/documents/1758d87f13dd7ef54ab7d170/w/29867918370809955f7674fe/e/a0d6977bb59d3b3c4eb5a3c6![Capture2](https://github.com/lavishlaiii3/engineering-3/assets/143545115/7e83571b-7e38-40b5-9a3e-3f82fe69ba68)


### Reflection
This assignment wasn't that bad I struggled a lot with adding the tube in between the cylinders but Mr. Miller helped and showed me how to use section view. Making the top and bottom cap was pretty simple the directions were clear and I'm familiar with the tools we needed to make the cap. It also gave me a insight into how the engineering test is going to be. 

