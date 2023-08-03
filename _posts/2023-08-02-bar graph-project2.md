---
layout: post
title: "Let's create circuit schematics on LTspice(while dealing with unexpected error)!"
tags: challenging work
catergories: LTspice
---
for starter: I created a voltage divider by following this YT video [LTSpice Tutorial - EP1 Getting started](https://youtu.be/JRcyHuyb1V0)
<img src="https://raw.githubusercontent.com/TomatoNut/myblog/main/voltage%20divisor.png" alt="voltage divider" width="400px" height="350px">

### Creating a circuit schematic for the Bar graph project using LTspice
Why even doing this?
- Despite having never used LTspice before, I know that it is a great tool for circuit analysis, which I am curious about.
- Bar graph project utilizes the principle of parallel circuits and if we do not include potentiometer, the circuit will be quite manageable for beginners like myself to put together in a schematic.
<imag src="https://raw.githubusercontent.com/TomatoNut/myblog/main/bar%20graph%20schematic.png" width= "300px" height="500px">
I decided to reduce the number of LEDs into 4, with them being LEDs of the 4 different colours used in the Bar graph project: white, green, yellow, red(counting from the bottom)
After putting in the values of the resistance and current ratings(note that different coloured LEDs have different values and the values were found online), I ran the simulator.
And... errors occured.
<img src= "https://raw.githubusercontent.com/TomatoNut/myblog/main/error1-no%20model%20found.png" width="300px" height="150px">
<img src="https://raw.githubusercontent.com/TomatoNut/myblog/main/error2-led%20current%20ratings.png" width="400px" height="350px">
After researching, I found out that the built-in diodes in LTspice, do not use current ratings/ average forward current(IF(AV)) as a parameter. However, it uses the forward voltage drop(VF) and other parameters, which is still able to represent a general didoe's behavior. Therefore, if we still would like to replicate our real-life circuit onto LTspice, we might need a more detailed diode model to represent the LEDs with different current ratings.

However, I am not giving up!
I still would like to find out the resistors with suitable values that I should use for each coloured LED, I performed calculation by hand:


