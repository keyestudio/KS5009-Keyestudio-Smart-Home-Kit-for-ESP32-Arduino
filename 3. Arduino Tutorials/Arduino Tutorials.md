# Arduino Tutorials

**Keyestudio IoT Smart Home Kit for ESP32**


## 1. Description
    
    As the rapid development of the Internet grows, various intelligent
    devices are gradually integrated into our daily life. For example,
    we can use RFID to open the door. In addition, the kitchen is
    equipped with a gas detection alarm, which alerts people to the
    danger when dangerous gas and large smoke are detected. When it
    detects rain, it can automatically collect clothes and close
    windows. All kinds of electrical equipment can be controlled by
    mobile phone, control lights, fans, air conditioning and so on.  
    
    In this connection, we seek to launch this smart home product with
    ESP32 control, which has a host of sensors and modules as well as
    networking function, making the relevant knowledge of the Internet
    more accessible to you.

## 2. Features

<!-- end list -->

1.  Elegant appearance

2.  A host of sensor modules

3.  Mobile phone APP network control

4.  Morse password door

5.  It can automatically close windows

6.  RFID function

7.  C language and MicroPython

<!-- end list -->

## 3. Parameters

![](media/e00562548e84b885ad18510b261ade05.png)

## 4. Installation of arduino IDE
    
    Please open the files below for arduino IDE installation, which
    contain arduino IDE installation, ESP32 environment installation,
    add library files as well as CH340 driver installation.

![](media/bf5635f6e0617d95966288f56c4027a4.png)

## 5. Installation of Structure 
    
    Please open the files below for structural installation
    
     ![](media/d325e5483eb04d5e324ed92baa79d034.png)

## 6. Projects

Sample code for all projects is in the folder, as shown below:

![](media/e6ed624571d83cfba100cf4f99e244a5.png)

### Project 1: Control LED

We will first learn how to control LED.

![](media/0cda68ae8719d9b6c1bb79d64160d31d.png)

1.  **Working Principle**

LED is also the light-emitting diode, which can be made into an
electronic module. It will shine if we control pins to output high
level, otherwise it will be off.  

2.  **[Parameter](C:/Users/NINGMEI/AppData/Local/youdao/dict/Application/8.10.7.0/resultui/html/index.html#/javascript:;)s**

|                 |          |
| --------------- | -------- |
| Working voltage | DC 3\~5V |
| Working current | \<20mA   |
| Power           | 0.1W     |

3.  **Control Pin**

|            |    |
| ---------- | -- |
| Yellow LED | 12 |

#### Project 1.1 **LED Flashing** 

1.  **Description**

We can make the LED pin output high level and low level to make the LED
flash.  

2.  **Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>#define led_y 12 //Define the yellow led pin to 12</p>
<p>void setup() </p>
<p>void loop() </p></td>
</tr>
</tbody>
</table>

3.  **Test Result**

After uploading the code , you can see white and yellow LEDs flashing
together.  

#### Project 1.2 Breathing LED

1.  **Description**

A“breathing LED”is a phenomenon where an LED's brightness smoothly
changes from dark to bright and back to dark, continuing to do so and
giving the illusion of an LED“breathing. However, how to control LED’s
brightness?

It makes sense to take advantage of PWM. Output the number of high level
and low level in unit time, the more time the high level occupies, the
larger the PWM value, the brighter the LED. 

![](media/704984700612966b997127cb9bde5c96.jpeg)

We provide the PWM output library file \< analogwrite.h \> for ESP32,
therefore solely a simple statement analogWrite(); can control the PWM
output.  

2.  **Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>#include &lt;analogWrite.h&gt; //Import PWM output library files</p>
<p>#define led_y 12 //Define LED pins</p>
<p>void setup()</p>
<p>void loop()</p>
<p>for(int i=255; i&gt;0; i--) //The for loop statement continues to decrease the value of variable i until it exits the loop at 0</p>
<p>analogWrite(led_y, i);</p>
<p>delay(3);</p>
<p>}</p>
<p>}</p></td>
</tr>
</tbody>
</table>

3.  **Test Result**

The LED gradually gets dimmer then brighter, cyclically, like human
breathe.

### Project 2: Table [Lamp](C:/Users/NINGMEI/AppData/Local/youdao/dict/Application/8.10.7.0/resultui/html/index.html#/javascript:;)

1.  **Description**

The common table lamp uses LED lights and buttons, which can control the
light on and off pressing the button.

 

2.  **Button Principle**

The button module is a digital sensor, which can only read 0 or 1. When
the module is not pressed, it is in a high level state, that is, 1, when
pressed, it is a low level 0. 

![](media/41f565d4f355abb96e105119660e80ba.png)

3.  **Pins of the Button**

|          |    |
| -------- | -- |
| Button 1 | 16 |
| Button 2 | 27 |

#### Project 2.1 Read the Button

**1. Description**

We will work to read the status value of the button and display it on
the serial monitor, so as to see it intuitively.  

2.  **Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>#define btn1 16</p>
<p>#define btn2 27</p>
<p>void setup() </p>
<p>void loop() </p></td>
</tr>
</tbody>
</table>

3.  **Test Result**

Open the serial monitor of the arduino IDE

![](media/7b790a6090abe48cc2599d3035d3a151.png)

Press the button again to see the change of the button state value, as
shown below:

![](media/07b8c2accc3f86ab0a853eee8fa3e58b.png)

#### Project 2.2. Table Lamp 

**1. Description**

For common simple table lamp, click the button it will be opened, click
it again, the lamp will be closed.  

2.  **Test Code**

Calculate the clicked button times and take the remainder of 2, you can
get 0 or 1 two state values.  

<table>
<tbody>
<tr class="odd">
<td><p>#define btn1 16</p>
<p>#define led_y 12</p>
<p>int btn_count = 0; //Used to count the clicked button times</p>
<p>void setup() </p>
<p>void loop() </p>
<p>}</p>
<p>}</p>
<p>boolean value = btn_count % 2; //Take the remainder of the value, you will get 0 or 1</p>
<p>if(value == 1)</p>
<p></p>
<p>else</p>
<p>}</p>
<p>}</p></td>
</tr>
</tbody>
</table>

3.  **Test Result**

Open the serial monitor and print out the clicked button times, then
click the button once, the LED will be on, click it again, it will be
off.  

![](media/a12e75e3ec7319757051795c827a7b24.png)

### Project 3: PIR Motion Sensor

**1. Description**

The PIR motion sensor has many application scenarios in daily life, such
as automatic induction lamp of stairs, automatic induction faucet of
washbasin, etc.  

It is also a digital sensor like buttons, which has two state

values 0 or 1.  And it will be sensed when people are moving.  

![](media/c1518252606b111bfa66878a2bfcc965.png)

2.  **Control Pin**

|                   |    |
| ----------------- | -- |
| PIR motion sensor | 14 |

#### Project 3.1 Read the PIR Motion Sensor

We will print out the value of the PIR motion sensor through the serial
monitor.

1.  **Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>#define pyroelectric 14</p>
<p>void setup() </p>
<p>void loop() </p></td>
</tr>
</tbody>
</table>

2.  **Test Result**

When you stand still in front of the sensor, the reading value is 0,
move a little, it will change to 1.

![](media/e50f0f6c666cdb14857511dccd71ed73.png)

#### Project 3.2 PIR Motion Sensor

If someone moves in front of the sensor, the LED will light up.  

1.  **Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>#define pyroelectric 14</p>
<p>#define led_y 12 //Define the yellow led pin to 12</p>
<p>void setup() </p>
<p>void loop() else</p>
<p>}</p></td>
</tr>
</tbody>
</table>

2.  **Test Result**

Move your hand in front of the sensor,  the LED will turn on. After 5s
of immobility, the LED lights will turn off.  

### Project 4: Play Music

**1. Description**

There is a audio power amplifier element in the car expansion board,
which is as an external amplification equipment to play music.

In this project, we will work to play a  piece of music by using it. 

**2. Component Knowledge**

**Passive Buzzer:** The audio power amplifier (like the passive buzzer)
does not have internal oscillation. When controlling, we need to input
square waves of different frequencies to the positive pole of the
component and ground the negative pole to control the power amplifier to
chime sounds of different frequencies.

![](media/2e6fd6b7975ef84ab94eee896161347b.png)

3.  **Control Pin**

|                |    |
| -------------- | -- |
| Passive Buzzer | 25 |

#### Project 4.1 Play Happy Birthday

**1. Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>#include &lt;ESP32Tone.h&gt;</p>
<p>#define buzzer_pin 25</p>
<p>void setup() </p>
<p>void loop() </p>
<p>void birthday()</p>
<p></p></td>
</tr>
</tbody>
</table>

**2. Test Result**

The passive buzzer will play happy Birthday.

#### Project 4.2 Music Box

we will make a music box and switch tunes by pressing buttons.  

**1. Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>#include &lt;ESP32Tone.h&gt;</p>
<p>#include &lt;musicESP32_home.h&gt;</p>
<p>music Music(25);</p>
<p>#define btn1 16</p>
<p>int btn_count = 0; //Used to count the clicked button times</p>
<p>boolean music_flag = 0;</p>
<p>void setup() </p>
<p>void loop() </p>
<p>switch(btn_count)</p>
<p> break;</p>
<p>case 2: if(music_flag == 1) break;</p>
<p>case 3: if(music_flag == 1) break;</p>
<p>}</p>
<p>btn_state = 0; //The button is released and exits the loop</p>
<p>}</p>
<p>}</p>
<p>}</p>
<p>}</p>
<p>}</p></td>
</tr>
</tbody>
</table>

**2. Test Result**

Click button 1 once, it will play a tetris, then click it again, it will
play Ode\_to\_Joy, after playing, click the button 1 for the third time,
it will play Christmas.  

### Project 5: Automatic Doors and Windows

1.  **Description**

Automatic doors and windows need power device, which will become more
automatic with a 180 degree servo and some sensors. Adding a raindrop
sensor, you can achieve the effect of closing windows automatically when
raining. If adding a RFID, we can realize the effect of swiping to open
the door and so on.  

2.  **Component Knowledge**
    
    **Servo:** Servo is a position servo
    [driver](C:/Users/NINGMEI/AppData/Local/youdao/dict/Application/8.10.7.0/resultui/html/index.html#/javascript:;)
    device consists of a housing, a circuit board, a coreless motor, a
    gear and a position detector.

Its working principle is that the servo receives the signal sent by MCU
or receiver and produces a reference signal with a period of 20ms and
width of 1.5ms, then compares the acquired DC bias voltage to the
voltage of the potentiometer and obtain the voltage difference output.

The IC on the circuit board judges the direction of rotation, and then
drives the coreless motor to start rotation. The power is transmitted to
the swing arm through the reduction gear, and the signal is sent back by
the position detector to judge whether the positioning has been reached,
which is suitable for those control systems that require constant angle
change and can be maintained.  

When the motor speed is constant, the potentiometer is driven to rotate
through the cascade reduction gear, which leads that the voltage
difference is 0, and the motor stops rotating. Generally, the angle
range of servo rotation is 0° --180 °.

The pulse period of the control servo is 20ms, the pulse width is 0.5ms
\~ 2.5ms, and the corresponding position is -90°\~ +90°.  Here is an
example of a 180° servo:  

![](media/708316fde05c62113a3024e0efb0c237.jpeg)

In general, servo has three lines in brown, red and orange. The brown
wire is grounded, the red one is a positive pole line and the orange one
is a signal line.

![](media/35084ae289a08e35bdb8c89ceb134ba4.png)

![](media/6cbf6f177ea204f7632b872497fde010.png)

3.  **Pin**

|                         |    |
| ----------------------- | -- |
| The servo of the window | 5  |
| The servo of the door   | 13 |

#### Project 5.1 Control the Door 

**1. Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>#include &lt;ESP32_Servo.h&gt;</p>
<p>Servo myservo; // create servo object to control a servo</p>
<p>// 16 servo objects can be created on the ESP32</p>
<p>int pos = 0; // variable to store the servo position</p>
<p>// Recommended PWM GPIO pins on the ESP32 include 2,4,12-19,21-23,25-27,32-33</p>
<p>int servoPin = 13;</p>
<p>void setup() </p>
<p>void loop() </p>
<p>for (pos = 180; pos &gt;= 0; pos -= 1) </p>
<p>}</p></td>
</tr>
</tbody>
</table>

**2. Test Result**

The servo of the door turns with the door, back and forth

#### Project 5.2 Close the Window

1.  **Description**
    
    We will work to use a servo and a raindrop sensor to make an device
    closing windows automatically when raining.  

2.  **Component Knowledge**

**Raindrop Sensor:** This is an analog input module, the greater the
area covered by water on the detection surface, the greater the value
returned (range 0\~4096). 

3.  **Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>#include &lt;ESP32_Servo.h&gt;</p>
<p>Servo myservo;</p>
<p>#define servoPin 5</p>
<p>#define waterPin 34</p>
<p>void setup() </p>
<p>void loop() </p>
<p>else </p>
<p>}</p></td>
</tr>
</tbody>
</table>

4.  **Test Result**

At first, the window opens automatically, and when you touch the
raindrop sensor with your hand (which has water on the skin), the window
will close.  

### Project 6: Atmosphere Lamp

1.  **Description**

The atmosphere lamp of smart home is 4 SK6812RGB LEDs. RGB LED belongs
to a simple luminous module, which can adjust the color to bring out the
lamp effect of different colors. Furthermore, it can be widely used in
buildings, bridges, roads, gardens, courtyards, floors and other fields
of decorative lighting and venue layout, Christmas, Halloween,
Valentine's Day, Easter, National Day as well as other festivals during
the atmosphere and other scenes.

In this experiment, we will make various lighting effects.  

2.  **Component Knowledge**
    
    From the schematic diagram, we can see that these four RGB LEDs are
    all connected in series. In fact, no matter how many they are, we
    can use a pin to control a RGB LED and let it display any color.
    Each RGBLED is an independent pixel, composed of R, G and B colors,
    which can achieve 256 levels of brightness display and complete the
    full true color display of 16777216 colors. 
    
    What’s more, the pixel point contains a data latch signal shaping
    amplifier drive circuit and a signal shaping circuit, which
    effectively ensures the color of the pixel point light is highly
    consistent.
    
    ![](media/86e292d0666046b72a1e0e68adfb17e8.png)
    
    ![](media/c0df93f61c6b9272f62b1847ccfbdb10.png)

3.  **Pin**

|        |    |
| ------ | -- |
| SK6812 | 26 |

#### Project 6.1 Control SK6812

We will control SK6812 to display various lighting effects.

**1. Test Code**

Please open the provided test code pj6\_1\_SK6812, as shown in the image
below:  

![](media/b5485e8a24aebc8fee5ed77ed3f9108f.png)

**2. Test Result**

The atmosphere lamps of the smart home will display a variety of colors
and light effects.

#### Project 6.2 Button 

1.  **Description**

There are two buttons to switch the color of the atmosphere lamp.

2.  **Test Code**

Please open the provided test code pj6\_2\_btn\_6812, as shown below:  

![](media/0fdb94dd498f88a55cd57c7603fe43c6.png)

3.  **Test Result**

We can switch the color of the atmosphere lamp by clicking buttons 1 and
2.

### Project 7: Fan

1.  **Description**

In this project, we will learn how to make a small fan.

2.  **Component Knowledge**

The small fan uses a 130 DC motor and safe fan blades.  You can use PWM
output to control the fan speed.  

![](media/33da52918e88862a94035d61a9050f2e.png)

3.  **Control Method**

Two pins are required to control the motor of the fan, one for INA and
two for INB.  The PWM value range is 0\~255. When the PWM output of the
two pins is different, the fan can rotate.  

|                    |                                                                                                                                |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------ |
| INA - INB \<= -45  | Rotate clockwise                                                                                                               |
| INA - INB \>= 45   | Rotate [anticlockwise](C:/Users/NINGMEI/AppData/Local/youdao/dict/Application/8.10.7.0/resultui/html/index.html#/javascript:;) |
| INA == 0, INB == 0 | Stop                                                                                                                           |

4.  **Control Pins**

|     |    |
| --- | -- |
| INA | 19 |
| INB | 18 |

#### Project 7.1 Control the Fan 

We can control the
[anticlockwise](C:/Users/NINGMEI/AppData/Local/youdao/dict/Application/8.10.7.0/resultui/html/index.html#/javascript:;)
and clockwise rotation speed of the fan.

**1. Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>#include &lt;analogWrite.h&gt;</p>
<p>#define fanPin1 19</p>
<p>#define fanPin2 18</p>
<p>void setup() </p>
<p>void loop() </p></td>
</tr>
</tbody>
</table>

**2. Test Result**

The fan will rotate clockwise and
[anticlockwise](C:/Users/NINGMEI/AppData/Local/youdao/dict/Application/8.10.7.0/resultui/html/index.html#/javascript:;)
at different

speeds.

#### Project 7.2 Switch On or Off the Fan 

One button switches the fan on and the other button controls the speed
of the fan.

**1. Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>#include &lt;analogWrite.h&gt;</p>
<p>#define fanPin1 19</p>
<p>#define fanPin2 18</p>
<p>#define btn1 16</p>
<p>int btn_count = 0; //Used to count the clicked button times</p>
<p>#define btn2 27</p>
<p>int btn_count2 = 0;</p>
<p>int speed_val = 130; //Define the speed variables</p>
<p>void setup() </p>
<p>void loop() </p>
<p>}</p>
<p>}</p>
<p>boolean value = btn_count % 2; //Take the remainder of the value, you will get 0 or 1</p>
<p>while(value == 1)</p>
<p></p>
<p>switch(btn_count2)</p>
<p></p>
<p>btn_state2 = 0;</p>
<p>}</p>
<p>}</p>
<p>}</p>
<p>}</p>
<p>boolean btn1_val = digitalRead(btn1);</p>
<p>if(btn1_val == 0) //If the button is pressed</p>
<p></p>
<p>}</p>
<p>}</p>
<p>}</p></td>
</tr>
</tbody>
</table>

**2. Test Result**

Click button 1, the fan starts to rotate, click button 2, the

speed can be adjusted(there are three different speeds), press the
button 1 again, the fan stops. 

### Project 8: LCD1602 Display

1.  **Description**

As we all know, screen is one of the best ways for people to interact
with electronic devices.  

2.  **Component Knowledge**

1602 is a line that can display 16 characters. There are two lines,
which use IIC communication protocol.  

![](media/066e093f1711ada67d3309ddc9bdc66e.png)

3.  **Control Pins**

|     |     |
| --- | --- |
| SDA | SDA |
| SCL | SCL |

#### Project 8.1 Display [Character](C:/Users/NINGMEI/AppData/Local/youdao/dict/Application/8.10.7.0/resultui/html/index.html#/javascript:;)s

**1. Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>#include &lt;Wire.h&gt;</p>
<p>#include &lt;LiquidCrystal_I2C.h&gt;</p>
<p>LiquidCrystal_I2C mylcd(0x27,16,2);</p>
<p>void setup()</p>
<p>void loop()</p></td>
</tr>
</tbody>
</table>

**2. Test Result**

The first line of the LCD1602 shows hello and the second line shows
keyestudio.  

#### Project 8.2 Dangerous Gas Alarm 

**1. Description**

When a gas sensor detects a high concentration of dangerous gas, the
buzzer will sound an alarm and the display will show dangerous.

 

**2. Component Knowledge**

**MQ2 Smoke Sensor**: It is a gas leak monitoring device for homes and
factories, which is suitable for liquefied gas, benzene, alkyl, alcohol,
hydrogen as well as smoke detection.  Our sensor leads to digital pin D
and analog output pin A, which is connected to D as a digital sensor in
this project .  

![](media/4550c4935e6c08e595a1e8707b54b551.png)

**3. Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>#include &lt;Wire.h&gt;</p>
<p>#include &lt;LiquidCrystal_I2C.h&gt;</p>
<p>LiquidCrystal_I2C mylcd(0x27,16,2);</p>
<p>#define gasPin 23</p>
<p>#define buzPin 25</p>
<p>boolean i = 1;</p>
<p>boolean j = 1;</p>
<p>void setup()</p>
<p>void loop()</p>
<p>digitalWrite(buzPin,HIGH);</p>
<p>delay(1);</p>
<p>digitalWrite(buzPin,LOW);</p>
<p>delay(1);</p>
<p>}</p>
<p>else</p>
<p>}</p>
<p>}</p></td>
</tr>
</tbody>
</table>

4.  **Test Result**

The screen displays "safety" in normal state. However, when the gas
sensor detects some dangerous gases, such as carbon monoxide, at a
certain concentration, the buzzer will sound an alarm and the screen
displays "dangerous".  

### Project 9: Temperature and Humidity Sensor

1.  **Component Knowledge**

Its communication mode is serial data and single bus. The temperature
measurement range is -20 \~ +60℃, accuracy is ±2℃. However, the humidity
range is 5 \~ 95%RH, the accuracy is ±5%RH.  

![](media/0b9c44c3e4f3706638b9cf15871b861c.png)

2.  **Control Pin**

|                                 |    |
| ------------------------------- | -- |
| Temperature and Humidity Sensor | 17 |

#### Project 9.1 Temperature and Humidity Tester

**1. Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>//**********************************************************************************</p>
<p>/*</p>
<p>* Filename : xht11</p>
<p>* Description : Read the temperature and humidity values of XHT11.</p>
<p>* Auther : http//www.keyestudio.coml</p>
<p>*/</p>
<p>#include &lt;Wire.h&gt;</p>
<p>#include &lt;LiquidCrystal_I2C.h&gt;</p>
<p>LiquidCrystal_I2C mylcd(0x27,16,2);</p>
<p>#include "xht11.h"</p>
<p>xht11 xht(17);</p>
<p>unsigned char dht[4] = ;//Only the first 32 bits of data are received, not the parity bits</p>
<p>void setup() </p>
<p>void loop()  else </p>
<p>delay(1000); //It takes 1000ms to wait for the device to read</p>
<p>}</p>
<p>//**********************************************************************************</p></td>
</tr>
</tbody>
</table>

**2. Test Result**

The LCD1602 displays the temperature (T = \*\* ° C) and humidity (H =
\*\* %RH). When you breathe into the T/H sensor, you can see that the
humidity rises.  

### Project 10: RFID RC522 Module

1.  **Component Knowledge**

Radio frequency identification, the card reader is composed of a radio
frequency module and a high-level magnetic field. The Tag transponder is
a sensing device, which doesn’t contain a battery. It only contains tiny
integrated circuit chips and media for storing data and antennas for
receiving and transmitting signals.

To read the data in the tag, first put it into the reading range of the
card reader. The reader will generate a magnetic field, which can
produce electricity according to Lenz's law, then the RFID tag will
supply power, thereby activating the device.

![](media/982ac6a9da0e8f55465ca5a969ac0dfe.png)

2.  **Control Pins**
    
    Use IIC communication

|     |     |
| --- | --- |
| SDA | SDA |
| SCL | SCL |

#### Project 10.1 Open the Door

**1. Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>//**********************************************************************************</p>
<p>/*</p>
<p>* Filename : RFID</p>
<p>* Description : RFID reader UID</p>
<p>* Auther : http//www.keyestudio.com</p>
<p>*/</p>
<p>#include &lt;Wire.h&gt;</p>
<p>#include &lt;LiquidCrystal_I2C.h&gt;</p>
<p>LiquidCrystal_I2C mylcd(0x27,16,2);</p>
<p>#include &lt;ESP32_Servo.h&gt;</p>
<p>Servo myservo;</p>
<p>#include &lt;Wire.h&gt;</p>
<p>#include "MFRC522_I2C.h"</p>
<p>// IIC pins default to GPIO21 and GPIO22 of ESP32</p>
<p>// 0x28 is the i2c address of SDA, if doesn't match，please check your address with i2c.</p>
<p>MFRC522 mfrc522(0x28); // create MFRC522.</p>
<p>#define servoPin 13</p>
<p>#define btnPin 16</p>
<p>boolean btnFlag = 0;</p>
<p>String password = "";</p>
<p>void setup() </p>
<p>void loop() </p>
<p>}</p>
<p>return;</p>
<p>}</p>
<p>// select one of door cards. UID and SAK are mfrc522.uid.</p>
<p>// save UID</p>
<p>Serial.print(F("Card UID:"));</p>
<p>for (byte i = 0; i &lt; mfrc522.uid.size; i++) </p>
<p>if(password == "17121741227") //The card number is correct, open the door</p>
<p></p>
<p>else //The card number is wrong，LCD displays error</p>
<p></p>
<p>//Serial.println(password);</p>
<p>}</p>
<p>void ShowReaderDetails() </p>
<p>}</p>
<p>//**********************************************************************************</p></td>
</tr>
</tbody>
</table>

**2. Test Result**

Close the provided card to the RFID induction area, the door will turn
and open, and LCD1602 shows "The door is open". Click button 1 and the
door turns and closes. However, when swiping another blue induction
block, the LCD1602 shows "Error".  

### Project 11: [Morse](C:/Users/NINGMEI/AppData/Local/youdao/dict/Application/8.10.7.0/resultui/html/index.html#/javascript:;) [Code](C:/Users/NINGMEI/AppData/Local/youdao/dict/Application/8.10.7.0/resultui/html/index.html#/javascript:;) 

Morse code, also known as Morse password, is an on-again, off-again
signal code that expresses different letters, numbers, and punctuation
marks in different sequences. Now we use it as our password gate.

The Morse code corresponds to the following characters:

![](media/1a5e70c0d091e2617acbfc274827b4fd.png)

#### Project 11.1 Morse Code Open the Door

**1. Description**

We use ![](media/9491f7768f28ee4901e6fdb83632c27c.png)as the correct password. What’s more,
there is a button library file OneButton, which is very simple to click,
double click, long press and other functions. For Morse password, click
is“.”, long press and release is “-”.  

**2. Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>#include &lt;Wire.h&gt;</p>
<p>#include &lt;LiquidCrystal_I2C.h&gt;</p>
<p>LiquidCrystal_I2C mylcd(0x27,16,2);</p>
<p>#include "OneButton.h"</p>
<p>// Setup a new OneButton on pin 16.</p>
<p>OneButton button1(16, true);</p>
<p>// Setup a new OneButton on pin 27.</p>
<p>OneButton button2(27, true);</p>
<p>#include &lt;ESP32_Servo.h&gt;</p>
<p>Servo myservo;</p>
<p>int servoPin = 13;</p>
<p>String password = "";</p>
<p>String correct_p = "-.-"; //The correct password for the password door</p>
<p>// setup code here, to run once:</p>
<p>void setup() </p>
<p>void loop() </p>
<p>// ----- button 1 callback functions</p>
<p>// This function will be called when the button1 was pressed 1 time (and no 2. button press followed).</p>
<p>void click1()  // click1</p>
<p>// This function will be called once, when the button1 is released after being pressed for a long time.</p>
<p>void longPressStop1()  // longPressStop1</p>
<p>// ... and the same for button 2:</p>
<p>void click2() </p>
<p>else</p>
<p></p>
<p>password = "";</p>
<p>} // click2</p>
<p>void longPressStop2()  // longPressStop2</p></td>
</tr>
</tbody>
</table>

3.  **Test Result**

At first, the LCD1602 displays "Enter password", then click or long
press button 1 to tap the password. If we input the correct password
"-.-", then click button 2, the door will open, and the LCD1602 will
display "open".

If other incorrect passwords are entered, the door will not move, the
LCD1602 will display “error” and then “enter again” 2s later.
Furthermore, long press button 2 can close the door.  

### Project 12: WiFi 

The easiest way to access the Internet is to use a WiFi to connect. The
ESP32 main control board comes with a WiFi module, making our smart home
accessible to the Internet easily.

![](media/f74baff97695aa2ee33a8c19370d2547.png)

#### Project 12.1 Smart Home 

**1. Description**

We connect the smart home to a LAN, which is the WiFi in your home or
the hot spot of your phone. After the connection is successful, an
address will be assigned, which can be used for communication. We will
print the assigned address in the serial monitor.  

**2. Test Code**

Note: ssiD and password in the code should be filled with your own WiFi
name and password.  

![](media/12bde88b91fc863585343bca76b0daa6.png)

<table>
<tbody>
<tr class="odd">
<td><p>#include &lt;Arduino.h&gt;</p>
<p>#include &lt;WiFi.h&gt;</p>
<p>#include &lt;ESPmDNS.h&gt;</p>
<p>#include &lt;WiFiClient.h&gt;</p>
<p>String item = "0";</p>
<p>const char* ssid = "ChinaNet-2.4G-0DF0";</p>
<p>const char* password = "ChinaNet@233";</p>
<p>WiFiServer server(80);</p>
<p>void setup() </p>
<p>Serial.println("");</p>
<p>Serial.print("Connected to ");</p>
<p>Serial.println(ssid);</p>
<p>Serial.print("IP address: ");</p>
<p>Serial.println(WiFi.localIP());</p>
<p>server.begin();</p>
<p>Serial.println("TCP server started");</p>
<p>MDNS.addService("http", "tcp", 80);</p>
<p>}</p>
<p>void loop() </p>
<p>while(client.connected() &amp;&amp; !client.available())</p>
<p>String req = client.readStringUntil('\r');</p>
<p>int addr_start = req.indexOf(' ');</p>
<p>int addr_end = req.indexOf(' ', addr_start + 1);</p>
<p>if (addr_start == -1 || addr_end == -1) </p>
<p>req = req.substring(addr_start + 1, addr_end);</p>
<p>item=req;</p>
<p>Serial.println(item);</p>
<p>String s;</p>
<p>if (req == "/") //Browser accesses address can read the information sent by the client.println(s);</p>
<p></p></td>
</tr>
</tbody>
</table>

**3. Test Result**

If the WiFi is connected successfully, the serial monitor will print out
the assigned IP address.  

![](media/978de9389d1f427010faadcfe2669e08.png)

Open a browser to access the IP address, then we will read the contents
of the string S sent out by the client.println(s); in the code.

![](media/cd11492bc27df711a04eafb7696f0dfb.png)

#### Project 12.2 Control Smart Home

**1. Description**

In this project, we will learn how to realize different functions of the
smart home through accessing different strings under the address. There
is a LCD screen that can print out the IP address, which is much more
convenient.  

**2. Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>#include &lt;Arduino.h&gt;</p>
<p>#include &lt;WiFi.h&gt;</p>
<p>#include &lt;ESPmDNS.h&gt;</p>
<p>#include &lt;WiFiClient.h&gt;</p>
<p>String item = "0";</p>
<p>const char* ssid = "ChinaNet-2.4G-0DF0";</p>
<p>const char* password = "ChinaNet@233";</p>
<p>WiFiServer server(80);</p>
<p>#include &lt;Wire.h&gt;</p>
<p>#include &lt;LiquidCrystal_I2C.h&gt;</p>
<p>LiquidCrystal_I2C mylcd(0x27,16,2);</p>
<p>#include &lt;analogWrite.h&gt;</p>
<p>#define fanPin1 19</p>
<p>#define fanPin2 18</p>
<p>#define led_y 12 //Define the yellow led pin to 12</p>
<p>void setup() </p>
<p>Serial.println("");</p>
<p>Serial.print("Connected to ");</p>
<p>Serial.println(ssid);</p>
<p>Serial.print("IP address: ");</p>
<p>Serial.println(WiFi.localIP());</p>
<p>server.begin();</p>
<p>Serial.println("TCP server started");</p>
<p>MDNS.addService("http", "tcp", 80);</p>
<p>mylcd.setCursor(0, 0);</p>
<p>mylcd.print("ip:");</p>
<p>mylcd.setCursor(0, 1);</p>
<p>mylcd.print(WiFi.localIP()); //LCD displays the ip adress</p>
<p>}</p>
<p>void loop() </p>
<p>while(client.connected() &amp;&amp; !client.available())</p>
<p>String req = client.readStringUntil('\r');</p>
<p>int addr_start = req.indexOf(' ');</p>
<p>int addr_end = req.indexOf(' ', addr_start + 1);</p>
<p>if (addr_start == -1 || addr_end == -1) </p>
<p>req = req.substring(addr_start + 1, addr_end);</p>
<p>item=req;</p>
<p>Serial.println(item);</p>
<p>String s;</p>
<p>if (req == "/") //Browser accesses address can read the information sent by the client.println(s);</p>
<p></p>
<p>if(req == "/led/on") //Browser accesses the ip address/led/on</p>
<p></p>
<p>if(req == "/led/off") //Browser accesses the ip address/led/off</p>
<p></p>
<p>if(req == "/fan/on") //Browser accesses the ip address/fan/on</p>
<p></p>
<p>if(req == "/fan/off") //Browser accesses the ip address/fan/off</p>
<p></p>
<p>//client.print(s);</p>
<p>client.stop();</p>
<p>}</p></td>
</tr>
</tbody>
</table>

**3. Test Result**

If the smart home is successfully connected to WiFi, the LCD screen will
display the assigned address.  

![](media/b61227cbbfd35940c62fac04a680484e.png)

Accessing address must add / led/on when using the browser, such as my
address is 192.168.0.129/ led/on. Then the smart home LED lights will be
turned on, if accessing 192.168.0.129/ led /off, then the LED lights
will be off.  

![](media/2788e68263a21922bd1f2178748db72b.png)

When the browser accesses 192.168.0.129/fan/ on, the fan of

the smart home will be turned on and at 192.168.0.129/fan/ off will be
turned off.

![](media/1af74f12f1a18d08dfc4c88f0b65f89b.png)

### Project 13: Mobile Phone APP

**Download APP**

**Android APP：**

The Android apk installation package is available in our resource pack,
as shown below:

![](media/e1ad649f98cab75e4619b8fc1ca1e24a.png)

Download from Google play:

Please search for keyes IoT home on Google play to download it.  

**Icon:  **

![](media/ce17c63fa9d88b5981779202e4292b36.png)

APP
[Interface](C:/Users/NINGMEI/AppData/Local/youdao/dict/Application/8.10.7.0/resultui/html/index.html#/javascript:;)

![](media/8e7c339852876017b41a39d5a0b31323.png)

**Download iOS APP**

Please search for keyes IoT home on APP Store to download it.  

#### Project 13.1 Test APP

**1. Description**

We will use APP to control the smart home LED lights and fan switches.

**2. Test Code**

<table>
<tbody>
<tr class="odd">
<td><p>#include &lt;Arduino.h&gt;</p>
<p>#include &lt;WiFi.h&gt;</p>
<p>#include &lt;ESPmDNS.h&gt;</p>
<p>#include &lt;WiFiClient.h&gt;</p>
<p>String item = "0";</p>
<p>const char* ssid = "ChinaNet-2.4G-0DF0";</p>
<p>const char* password = "ChinaNet@233";</p>
<p>WiFiServer server(80);</p>
<p>#include &lt;Wire.h&gt;</p>
<p>#include &lt;LiquidCrystal_I2C.h&gt;</p>
<p>LiquidCrystal_I2C mylcd(0x27,16,2);</p>
<p>#include &lt;analogWrite.h&gt;</p>
<p>#define fanPin1 19</p>
<p>#define fanPin2 18</p>
<p>#define led_y 12 //Define the yellow led pin to 12</p>
<p>void setup() </p>
<p>Serial.println("");</p>
<p>Serial.print("Connected to ");</p>
<p>Serial.println(ssid);</p>
<p>Serial.print("IP address: ");</p>
<p>Serial.println(WiFi.localIP());</p>
<p>server.begin();</p>
<p>Serial.println("TCP server started");</p>
<p>MDNS.addService("http", "tcp", 80);</p>
<p>mylcd.setCursor(0, 0);</p>
<p>mylcd.print("ip:");</p>
<p>mylcd.setCursor(0, 1);</p>
<p>mylcd.print(WiFi.localIP()); //LCD displays ip adress</p>
<p>}</p>
<p>void loop() </p>
<p>while(client.connected() &amp;&amp; !client.available())</p>
<p>String req = client.readStringUntil('\r');</p>
<p>int addr_start = req.indexOf(' ');</p>
<p>int addr_end = req.indexOf(' ', addr_start + 1);</p>
<p>if (addr_start == -1 || addr_end == -1) </p>
<p>req = req.substring(addr_start + 1, addr_end);</p>
<p>item=req;</p>
<p>Serial.println(item);</p>
<p>String s;</p>
<p>if (req == "/") //Browser accesses address can read the information sent by the client.println(s);</p>
<p></p>
<p>if(req == "/led/on") //Browser accesses address ip address/led/on</p>
<p></p>
<p>if(req == "/led/off") //Browser accesses address ip address/led/off</p>
<p></p>
<p>if(req == "/fan/on") //Browser accesses address ip address/fan/on</p>
<p></p>
<p>if(req == "/fan/off") //Browser accesses address ip address/fan/off</p>
<p></p>
<p>//client.print(s);</p>
<p>client.stop();</p>
<p>}</p></td>
</tr>
</tbody>
</table>

**3. Test Result**

1\. Open the APP and select WIFI

![](media/ac7304f39a53b2318825db72e5085753.png)

2\. APP controls LED and the fan

The mobile phone and the smart home must share the same WiFi, or the
smart home connects to the hotspot of the mobile phone.  

APP input IP address (LCD1602 displays the assigned IP address), then
click connect, the connection is successful if ESP32 IP: 192.168......
is displayed.  

Next, you can click the LED, then the smart home LED will be turned on.
Click the fan button and the fan will be turned on, as shown below: 

![](media/aba40215ce81fc7c326f6666c67059b8.png)

#### Project 13.2 IoT Smart Home

**1. Description**

The IOT smart home connects to the family WiFi through

WiFi, and the mobile phone used for operation should also be connected
to the same WiFi.

What’s more, the smart home also can connect to the hotspot of the
mobile phone. If the connection is successful, the LCD1602 will display
the IP address. Using the phone APP to input the corresponding IP for
communication is

enable to realize the APP control of various functions of the smart
home.  

**2. Test Code**

Please refer to the sample code, as shown below:

![](media/547c1d768d1eb0dc27a85ea1d0bffcce.png)

**3. Test Result**

![](media/a94cd80683c4eecb3c1bcabd4a60747d.png)

## 7. Resources

Download code, libraries and more details, please refer to the following
link:

https://fs.keyestudio.com/KS5009
