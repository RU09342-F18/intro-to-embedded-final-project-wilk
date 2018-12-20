#  Door-counter
### Final Project for Introduction to Embedded Systems
### Team Members: Patrick Wilk

## Description
The door counter is a proximity sensor which uses ultrasonic waves to detect the distance of an object. When the distance is less than the set value, this means someone has passed by and it counts up. The idea was thought to be implemeted in the Rowan gymnassium where the students currently use a button to count up. 
## UART communication 
Users can download RealTerm, a program which can read values through UART.

## Software
### main.c
This is the file for the MSP430G2553 microcontroller. Using Code Composer Studio, this file is flashed to controller which will then process the inputs and outputs of ultrasonic sensor. 
• UART() is the setup for serial UART connection that sends data to the device which also sends data to the microcontroller.
• PINS() GPIO pins to the sensors as inputs and outputs.
• ToggleRed() on-board LED is On when the sensor reads a distance below the set value 

One interrupt is used to constanlty check for distance and when the distance is less than the one set, it resets. Another interrupt is used to restart the count whent the device receives a "0" from the user


## Circuit Design
### MSP-EXP430G2553 Microcontroller
The microcontroller is the main processing unit for the Door Counter, using the input and output of the sensors to read distance in real time. The microcontroller detects input from sensors on a high signal.

### Ultrasonic sensor
The Ultrasonic sensor send pulses in 10 micro-second increments. When the sensor recieves the pulse, it will generate a 8 cycles of sonic burst independed from microcontroller. Sent ECHO pulse back to microcontroller are measured. The sensor has 4 pins. TRIG is connected to P1.4 (output) and ECHO is connected to P1.3 (input). The other two pins are used to power the senor, ground and 5V source. 

### Circuit Diagram
<img src="https://github.com/RU09342-F18/intro-to-embedded-final-project-russells-muscle/blob/master/FinalProjSchem.PNG" height="500" width="665">

## Parts List
• 1 MSP-EXP430G2553 Microcontroller

• 1 1kΩ resistor
  
• 1 2kΩ Resistor
  
• 1 Ultrasonic LM324 Sensor 

• 1 Solderless Breadboard
