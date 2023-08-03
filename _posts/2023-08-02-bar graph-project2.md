---
layout: post
title: "Let's create circuit schematics on LTspice(while dealing with unexpected error)!"
tags: challenging work
catergories: LTspice
---
for starter: I created a voltage divider by following this YT video [LTSpice Tutorial - EP1 Getting started](https://youtu.be/JRcyHuyb1V0)
<img src="https://raw.githubusercontent.com/TomatoNut/myblog/main/voltage%20divisor.png" alt="voltage divider" width="400px" height="350px">

### Creating a circuit schematic for the Bar graph project using LTspice
<imag src="https://raw.githubusercontent.com/TomatoNut/myblog/main/bar%20graph%20schematic.png" width= "300px" height="500px">
I decided to reduce the number of LEDs into 4, with them being LEDs of the 4 different colours used in the Bar graph project: white, green, yellow, red(counting from the bottom)
After putting in the values of the resistance and current ratings(note that different coloured LEDs have different values), I ran the simulator.
And... errors occured.
<img src= "https://raw.githubusercontent.com/TomatoNut/myblog/main/error1-no%20model%20found.png" width="300px" height="150px">
<img src="https://raw.githubusercontent.com/TomatoNut/myblog/main/error2-led%20current%20ratings.png" width="400px" height="350px">
After researching, I found out that the built in'D' diode did not designed to handle current ratings/ average forward current(IF(AV)). However, it uses the forward voltage drop(VF).

