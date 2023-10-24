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

## NextAssignment

### Description & Code Snippets
Write a couple sentences here, describing this assignment, and make sure that you hit these two points:
* What was the goal of the assignment?
* How did you accomplish that goal?
  How you accomplished the goal is NOT a reflection, it is you telling the reader how to do this assignment, in broad strokes.

  Your description is the right place to draw the reader's attention to any important chunks of code. Here's how you make code look like code:

```python
Code goes here

```

**Lastly, please end this section with a link to your code or file.**  

### Evidence

### Wiring
[tinkercad.com](https://www.tinkercad.com/learn/circuits).  If you can't find the particular part you need, get creative, and just drop a note into the circuit diagram, explaining.
For example, I use an Arduino Uno to represent my Circuitpython device but write a note saying which board I'm actually using.
Then post an image here.   [Here's a quick tutorial for all markdown code, like making links](https://guides.github.com/features/mastering-markdown/)
### Reflection
Don't just tell the reader what went wrong or was challenging!  Describe how you figured it out, share the things that helped you succeed (tutorials, other people's repos, etc.), and then share what you learned from that experience.  **Your underlying goal for the reflection, is to concisely pass on the RIGHT knowledge that will help the reader recreate this assignment better or more easily.  Pass on your wisdom!**



## Onshape_Assignment_Template

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

 
