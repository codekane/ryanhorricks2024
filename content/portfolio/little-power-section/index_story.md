---
title: "Little: Power Section"
description: "Custom ESP32-based PCB, and Charging Circuit"
summary: "Custom ESP32-based PCB, featuring a space-limited lithium-ion Charging Circuit, a TPS63001 3V3 Switching Regulator, a USB-C port, I2S Microphone, and extremely space-limited design."
slug: "little-power"
date: "2026-03-03 00:00:00-0700"
lastmod: "2026-09-08"
image: main.png
draft: false
---
I guess I need to write about this. 
To say something good about myself, and what I'm working on. 
As a form of self-love.

This is a project I started working on in... March of 2026. I was in the Cameron Highlands, 
working some bullshit volunteer job that left me with vast quantities of time sitting at a 
desk, and vast other quantities of time with a relatively cool climate, big desks, and nothing 
else to do besides drink, or play volleyball (neither of which I was actually doing).

So. I worked. I made it... the top priority. But why?

I was in Bangkok, over New Years, and while I was there I bought a pair of cat ears for 20 baht. 
They were very simple, made with a stainless steel flat metal band that went over the head, 
coupled to white furry ears, with fairy lights wound through them, connected to a small plastic 
control box containing 3 button cells, and a power switch.

I had been working on another project, related to AI (which I still need to write about), but...
I was up late one night, having just watched the Squid Games Season II finale, and I was in a 
very dark place, and I looked in my bag, and saw the cat ears, and I looked into my jar of 
lights, and I thought "hmmm...".

So I brought them downstairs, and traced around the ears to get their dimensions, and then, 
within that shape, I took some of my lights, and I arranged them in such a way as to make 
best use of the space available, amounting to 6 on each side, for a total of 12, with each 
lighting module being double-sided (building on my prior work), meaning a total of RGBW 
SK6812 LED's for each set.

As for how to power them, I've figured out how to score disposable vapes while I'm in Bangkok, 
and I've accumulated quite the collection of innards. Each one carries a 600 mAh 12650 battery, 
which, while small, could potentially be suitable (and in my head, to compensate for the fact 
that an ESP32 while transmitting is a power slut, I imagined using two of the batteries in 
parallel.

That gave me a power budget of between 600 and 1200 mAh, while still staying within reasonable 
constaints, regarding size, dimensions, and wearability.

Now, the obvious problem here became one of size. Unlike the source material, I need quite a 
bit more space, between charging circuitry, microcontrollers, sensors, controls, and batteries. 
This means that, unlike with the hat, I'd be very hard-pressed to assemble something out of 
modules, and to achieve sufficient miniaturization, I'd need to use a custom design.

I experimented with a few different charging IC's, before ultimately settling upon the BQ21040, 
chosen for reasons relating to its very compact size. My intention was to make this as small as 
possible, however I was also beginning to recognize my areas of ignorance. They were possible 
to ignore with a large, module-based design, but at the scale I Was working on (chosen dimensions 
were equivilent to a Lolin S3 Mini, except my design includes not just a battery charger, but a 
switching regulator -- it's quite a lot more that I'm packing in, compared to the source board, 
and while it's doable, I decided to hit the books.

Given that, at this point, I've evolved past the purview of "shit a Full Stack Developer can 
solder together by hand", and into proper electrical engineering, and given that electrical 
engineering is black magic, I read High Speed Digital Design: A Handbook of Black Magic by 
Howard Johnson. I also read the Printed Circuits Handbook, end-to-end, which isn't necessarily 
ideal, but between the two I Was able to look back on what I'd been doing, and see where I might 
need to think things through, and do some proper math.

Now, it was at this point that I realized that, despite my great efforts in the direction of 
miniaturization, it was actually not possible with my design. On this small board were two 
very major sources of heat - the linear regulator inside the battery charging IC, as well as 
the diode for the USB passthrough function. This proved to be a significant problem as the point 
where peak thermal discharge through the board would have both of these heat sources acting 
maximally. 

I modified the design, understanding the maximum design amperage to be 600 mAh dissipitation, 
in each of the charging, and system power sections. The design is very tight -- going outside 
of these tolerances will lead to thermal throttling of the charger, which would fail safe... 
the other power section would include the usb pass-through diode, which was swapped out for a 
part with superior thermal characteristics, and a lower voltage drop. It's in a section combined 
with the 3V3 switched mode regulator, however at 600 mAh, that's not expected to be a large 
contributor regarding power dissipitation (and in fact, given my intention to use the 3V3 rail 
to power the LED's, would likely improve it, by virtue of requiring a lower power draw at 5V 
to maintain 600 mA of output at 3.3V.

At this point, work on the power section could be considered to be solid. I took some time to 
research other potential options, hoping perhaps to be able to find a PowerPath IC that would 
combined a switching charge circuit for the li-ion battery (improving my thermal envelope), 
alongside a switched output for the system load when running on 5V (it turns out, this combination 
does not actually exist). Improvements to the design could be realized, nonetheless, by utilizing 
a switching regulator to handle battery charging, and the available PowerPath IC's do in fact 
constitute a pathway to improving thermal performance of both the charging section, as well as 
potentially obviating the need for the USB pass-through diode (itself the second-largest 
contributor to constraining our thermal envelope).


