---
layout: post
title: "Ardunio Bar graph"
tags: my first post
categories: Arduino
---

Today, I created an Arduino Bar graph using a row of 8 LEDs controlled controlled by a potentiometer. The analog input is achieved by turning the potentiometer, and depending on the direction of the turn, the LEDs light up or turn off one at a time in sequence.

components used:
- Ardunio UNO
- breadboard
- jumper wires
- 10k-ohm potentiometer
- 8 LEDs
- 8 220-ohm resistors

code used:
```
//set up variables
const int analogPin= A0; //pin from arduino board connected to potentiometer to take analogue input
const int ledTotal= 8; //we have 8 numbers of LEDs
int ledPins[]= {2,3,4,5,6,7,8,9}; //pins of arduino connected to the LEDs

void setup() {
  for (int lightedLed=0; lightedLed< ledTotal; lightedLed++){
    pinMode(ledPins[lightedLed], OUTPUT); //
  }
}

void loop() {
  int potentiometerReading = analogRead(analogPin); //get analog input
  int ledLevel = map(potentiometerReading, 0, 1023, 0, ledTotal);

  //during when lighted number is within the possible range of total number:
  for (int lightedLed=0; lightedLed < ledTotal; lightedLed++){
    if (lightedLed< ledLevel){ //only when potentiometer goes up by one step
    //we can light up
      digitalWrite(ledPins[lightedLed],HIGH);
  }
  else{
    //if not satisfied with the condition- within the range= we turn off the light
    digitalWrite(ledPins[lightedLed], LOW);
    }
  }
}
```

final presentation:
![arduino bar graph2](https://github.com/TomatoNut/myblog/assets/141178923/29d19c49-568e-4ee5-ad4f-98d8992191d8)
![arduino bar graph1](https://github.com/TomatoNut/myblog/assets/141178923/5b25affd-f4be-4704-9e43-816fea1c8d08)
[Check this video out to see how the final project works](https://youtu.be/sUpg7Z3-Dww)

