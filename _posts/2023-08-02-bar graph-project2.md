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
- Despite having never used LTspice before, I still acknowledge that it is a great tool for circuit analysis, which I am curious about.
- Bar graph project utilizes the principle of parallel circuits and by excluding the potentiometer for now, it becomes a much more manageable circuit for beginners like myself to put together in a schematic.
<imag src="https://raw.githubusercontent.com/TomatoNut/myblog/main/bar%20graph%20schematic.png" width= "300px" height="500px">
I decided to reduce the number of LEDs into 4, with them being LEDs of the 4 different colours used in the Bar graph project: white, green, yellow, red(counting from the bottom)
<img src="https://raw.githubusercontent.com/TomatoNut/myblog/main/bar%20graph%20schematic.png" width="400px" height="600"><br>
After putting in the values of the resistance and current ratings(note that different coloured LEDs have different values and the values were found online), I ran the simulator.<br>
And... errors occured.<br>

<img src= "https://raw.githubusercontent.com/TomatoNut/myblog/main/error1-no%20model%20found.png" width="300px" height="150px">
<img src="https://raw.githubusercontent.com/TomatoNut/myblog/main/error2-led%20current%20ratings.png" width="400px" height="350px"><br>

After researching, I found out that the built-in diodes in LTspice, do not use current ratings/ average forward current(IF(AV)) as a parameter. However, it uses the forward voltage drop(VF) and other parameters, which is still able to represent a general didoe's behavior. Therefore, if we would like to replicate our real-life circuit onto LTspice, we might need a more detailed diode model to represent the LEDs with different current ratings.<br>

In the end, I performed some calculations by hand to find out more about the suitable resistor values for each coloured LED:<br>
<br>
<img src="https://raw.githubusercontent.com/TomatoNut/myblog/main/bar%20graph%20resistor%20calculation.jpg" width="500px" height="500px"><br>  

From my calculations, I obtained the result which may help me to select the best suited (nearest standard) resistors:<br>
<ul>
  <li>for red LED: 170 ohms of resistance should be restricted</li>
  <li>for yellow LED: 140 ohms of resistance should be restricted</li>
  <li>for green LED: 100 ohms of resistance should be restricted</li>
  <li>for white LED: 80 ohms of resistance should be restricted</li>
</ul>
<br>
(this makes sense a lot to me that is why I should be using the 220 resistor instead of the 1k resistor!)
