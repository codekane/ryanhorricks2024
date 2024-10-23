---
title: "Lit Glamour Alpha"
slug: "lit-glamour-alpha"
description: "An ambitious plan: scale up to a dozen units within 6 months. Call it stupid, or brave; either way, assumptions were validated."
summary: "An ambitious plan: scale up to a dozen units within 6 months. Call it stupid, or brave; either way, assumptions were validated."
date: "2023-06-26"
image: panel.png

---
This project started, in its current iteration, on New Years Eve, 2022. In fact, it began 3 years earlier, in 
2019, when I made my first hat and found EVERYONE loved it.


{{< youtube Zr0bHCgStcE >}}

## Iteration 1

### Battery Charging
{{<gallery>}}
<img src="ESP8266_Li-Ion_Charger_First_Iteration.JPG" class="grid-w50"/>
<img src="ESP8266_Li-Ion_Charger_First_Iteration_Oops.JPG" class="grid-w50"/>
{{</gallery>}}

### Controls
{{<gallery>}}
<img src="ESP8266_Buttons_MK1.JPG" class="grid-w50"/>
<img src="ESP8266_Buttons_MK1_Breadboard.JPG" class="grid-w50"/>
{{</gallery>}}

### All-Together
{{<gallery>}}
<img src="Cowboy_Prototype_MK1.JPG" class="grid-w50"/>
{{</gallery>}}

{{< youtube 4AJq0cm-uJs >}}

### Sound Reactive Test

{{< youtube XG4DImLjiHw >}}

The device, at this point, is still based on the ESP8266, and is thus limited in its processing power. Despite 
that fact, it's nonetheless capable of wireless networking, and so I was able to connecting with with the 
Xlights application, which runs the processing on my local device, and outputs it over the network.

It looks amazing... And looking at it, I realize that, even now, the device I've created is not the very same 
as the one that had inspired my drive towards sound reactivity...


## The Lights
See, up until now, I was using a string of SK6812 RGBW LED's that I was able to acquire commercially. I went with 
these because they were IP68 rated -- meaning they'd be waterproof, dustproof, and perfectly capable of weathering 
the adverse environments prone to occur at a festival.

There was  problem, though -- they were very heavy. They served me well enough, in testing out my concept, and 
trialing out the lights, however the string in and of itself weighed in at over a pound. Weight has proven to be 
something of an albatross with this project, and so something needed to be done.

There was something more, though. The hat's came with 40 holes, however the strings contained 50 lights, and so what 
I did was to take the last 10 lights, and have them facing upwards, and what I found was that it was an effect 
I quite liked. This proved to be something of an inspiration for the next phase of the project:

### Double-Sided LED's
{{<gallery>}}
<img src="Heart_PCB_Schematic.JPG" class="grid-w50"/>
<img src="panel.jpg" class="grid-w50"/>

{{</gallery>}}

### Optical Simulations
At this juncture, given my aim was to completely in-source the weighty LED strings I'd been using, I'd beene planning 
to 3D print some optics. I went on a tangent here, and I satisfied a curiosity, as to how to go about simulating 
what the optics were going to do, without actually building them (because that seemede hard, and I still hadn't 
actually gotten into 3D Printing, at this point).

I drew inspiration from (this)[I cant Find it Right now, check history] blog article by (a cool sculptor guy), 
which lead me to try out Rhino3D. He suggested 3DOptix, however they seemed to want my money, so I wound up 
settling on FreeCAD instead, making use of the OpticsWorkbench plugin to trace my rays.

{{<gallery>}}
<img src="Casing_Optics_Simulation_White.JPG" class="grid-w50" />
<img src="Casing_Optics_Simulation_Full_Spectrum.JPG" class="grid-w50" />
{{</gallery>}}


## Iteration 2

{{<gallery>}}
<img src="ESP32_S3_Breadboard.JPG" class="grid-w50" />
<img src="ESP32_S3_Board_Layout_Fail.JPG" class="grid-w50" />
{{</gallery>}}

## The Final Countdown
{{<gallery>}}
<img src="Final_Countdown_Dual_Power_Supply.JPG" class="grid-w50" />
<img src="Final_Countdown_ESP32_S3_Breadboard.JPG" class="grid-w50" />
{{</gallery>}}

## Bunch of Random-Ass Images

{{<gallery>}}
<img src="eight-epoxy.jpg" class="grid-w50 md:grid-w33"/>
<img src="half-wired.jpg" class="grid-w50 md:grid-w33"/>
<img src="install-epoxy.jpg" class="grid-w50 md:grid-w33"/>
<img src="panel.jpg" class="grid-w50 md:grid-w33"/>
<img src="six-1.jpg" class="grid-w50 md:grid-w33"/>
<img src="six-two.jpg" class="grid-w50 md:grid-w33"/>
<img src="star.jpg" class="grid-w50 md:grid-w33"/>
<img src="three.jpg" class="grid-w50 md:grid-w33"/>
{{</gallery>}}

