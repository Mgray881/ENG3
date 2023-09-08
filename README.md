# ENG3
# CircuitPython
This repository will actually serve as an aid to help you get started with your own template.  You should copy the raw form of this readme into your own, and use this template to write your own.  If you want to draw inspiration from other classmates, feel free to check [this directory of all students!](https://github.com/chssigma/Class_Accounts).
## Table of Contents
* [Table of Contents](#TableOfContents)
* [Hello_CircuitPython](#Hello_CircuitPython)
* [CircuitPython_Servo](#CircuitPython_Servo)
* [CircuitPython_LCD](#CircuitPython_LCD)
* [NextAssignmentGoesHere](#NextAssignment)
---

## Hello_CircuitPython

### Description & Code
this asignment was to make a led flash a rainbow. i did this by wiring the led to the arduino then did the code.

Here's how you make code look like code:

```python
Code goes here

```


### Evidence


![spinningMetro_Optimized](https://user-images.githubusercontent.com/54641488/192549584-18285130-2e3b-4631-8005-0792c2942f73.gif)


And here is how you should give image credit to someone if you use their work:

Image credit goes to [Rick A](https://www.youtube.com/watch?v=dQw4w9WgXcQ&scrlybrkr=8931d0bc)



### Wiring
Make an account with your Google ID at [tinkercad.com](https://www.tinkercad.com/learn/circuits), and use "TinkerCad Circuits to make a wiring diagram."  It's really easy!  
Then post an image here.   [here's a quick tutorial for all markdown code, like making links](https://guides.github.com/features/mastering-markdown/)

### Reflection
What went wrong / was challenging, how'd you figure it out, and what did you learn from that experience?  Your ultimate goal for the reflection is to pass on the knowledge that will make this assignment better or easier for the next person.




## How To Fix the LCD power issue with Metro M4 boards.

### Description & Code

* **The symptoms:**  LCD acting weird OR trouble with usb connection / serial monitor / uploading / etc.
* **The problem :** The LCDs occasionally draw too much power when we turn on the boards, and that makes parts of its serial communications crash.
* **The Solution:** Add this code, and wire a switch up, like the wiring diagram below:



```python


```
### Wiring

![WiringSolution](images/I2C_M4_Solution.png)

##  Hello_CircuitPython

### Description & Code
This asignment was to make a led flash a rainbow. i did this by wiring the led to the arduino then did the code. I-+ lost my code, but this is similar to it. 
```C
void setup()  { 
 
} 
 
void loop()  {
 
 
  for(int b = 0 ; b <= 255; b=b+5) 
  { 
      for(int g = 0 ; g <= 255; g=g+5) 
    { 
      for(int r= 0 ; r <= 255; r=r+5) 
       { 
        analogWrite(9, b);         
        analogWrite(10, g);         
        analogWrite(11, r);    
        delay(10);
 
      } 
    }
  }
 
}
```
credit goes to [seeeddoc.github.io](https://seeeddoc.github.io/Arduino_Sidekick_Basic_Kit/)

### Evidence

### Wiring


<img src="https://seeeddoc.github.io/Arduino_Sidekick_Basic_Kit/img/Arduino_Sidekick_RGB_LED_Display.jpg"  style="width:500px;">


image credit goes to [https://seeeddoc.github.io(/Arduino_Sidekick_Basic_Kit/)
### Reflection
This asignment wasn't even hard i just had to look up how to wire a led. Cause i always wire first then do my code. 






## CircuitPython_LCD

### Description & Code

```python
Code goes here
import board
import time
import digitalio
from lcd.lcd import LCD
from lcd.i2c_pcf8574_interface import I2CPCF8574Interface

# turn on lcd power switch pin
lcdPower = digitalio.DigitalInOut(board.D8)
lcdPower.direction = digitalio.Direction.INPUT
lcdPower.pull = digitalio.Pull.DOWN

# Keep the I2C protocol from running until the LCD has been turned on
# You need to flip the switch on the breadboard to do this.
while lcdPower.value is False:
    print("still sleeping")
    time.sleep(0.1)

# Time to start up the LCD!
time.sleep(1)
print(lcdPower.value)
print("running")

i2c = board.I2C()
lcd = LCD(I2CPCF8574Interface(i2c, 0x27), num_rows=2, num_cols=16)


# Loop forever.
while True:
```

### Evidence

Pictures / Gifs of your work should go here.  You need to communicate what your thing does.

### Wiring


### Reflection


## circuitphython_servo

### Description & Code
This asignment was to get 2 buttons and when u press one button it goes to 180 and when u press the other one it goes to 0.
I got this working by getting the buttons working then add the code. 


```python
Code goes here
 Create a PWMOut object on Pin A2.
pwm = pwmio.PWMOut(board.A2, duty_cycle=2 ** 15, frequency=50)
# Create a servo object, my_servo.
my_servo = servo.Servo(pwm)

#button 1 turns to 180
btn = DigitalInOut(board.D11)
btn.direction = Direction.INPUT
btn.pull = Pull.DOWN

#button 2 turns to 0
btn2 = DigitalInOut(board.D6)
btn2.direction = Direction.INPUT
btn2.pull = Pull.DOWN

while True:
    # if button 1 is pressed then it will turn to 180
    if btn.value:
        my_servo.angle = 180
        time.sleep(0.02 )
        print("BTN1 is pressed") 
        # if button 2 is pressed it will turn to 0
    if btn2.value:
        my_servo.angle = 0
        time.sleep(0.05)
        print("BTN2 is pressed")


```

### Evidence

### Wiring
![buttonServoWiring](https://github.com/Mgray881/ENG3/assets/143528424/6c9d90a5-d094-45cc-bd45-f1122d33e2f1)



### Reflection
This asignment was hard but once i asked my classmate she told me what to do and it got easier. i used goggle to look up "how to wire a button." and i used adafruit to get the code.


## Circuirphtthon Distance Sensor

### Description & Code
This asignment was to measure the distance to an object using HC-SR04.
```python
Code goes here

```

### Evidence

### Wiring

### Reflection

## NextAssignment

### Description & Code

```python
Code goes here

```

### Evidence

### Wiring

### Reflection

## NextAssignment

### Description & Code

```python
Code goes here

```

### Evidence

### Wiring

### Reflection
