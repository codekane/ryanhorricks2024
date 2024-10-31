---
title: "3000 mAh Power Pack"
date: 2024-06-06
summary: "A much smaller, lighter source of power than my previous devives. It uses a TP4056 module for charging, together with a couple of mosfets, and a schottky diode to enable USB-Passthrough. This has proven safe, yet without voltage regulation I've encountered instabilities (and data corruption), so this is as much about what's been done well, as what must be done better."
lastmod: "2024-10-31"
tags:
    - "Lit"
---
## Foreword
I've always been cautious when it comes to batteries. When I first broached this project to some experienced electrical engineers, they 
looked at me as though I was a heretic, when I suggested my plan was to put lithium-ion batteries on top of people's heads.

I think that they're just old. I've since met more daring, adventurous people who had done exactly that, and done so quite successfully, 
having built a business, and launched several products using the technology.




## Parts
- (1) [TP4056 USB-C Charging Module](https://www.amazon.ca/TP4056-Battery-Charging-Protection-Indicator/dp/B0DGFBKWQN). This is being used not just to power the battery, but also for it's USB port to provide system power via a USB Pass-Through circuit.
- (2) [IRF4905 P-Channel Mosfet](https://www.amazon.ca/dp/B08WRY3HBV).
- (1) SPDT Switch. I scavenged this from a AA-Powered light string I got at the dollar store.
- (2) 10k Ohm Pull-Down Resistors. These are connected to the gate of the P-Channel Mosfets, pulling them down unless power from elsewhere in the circuit is provided to overwhelm the minimal flow provided through the resistor.
- (2) 100k Ohm Resistors. These are used to create a voltage divider, so as to make the peak 4.2V battery voltage possible to read from a 3.3V analog pin on the microcontroller.
- (1) 2-pin JST-XH Connector. This is used to provide a solid, detachable connection between the board, and the battery.
- (1) 6-pin JST-XH Connector. I don't actually need all six pins here. I'm using two for ground, one for switched battery voltage, and one for always-on battery voltage (value divided by two, to be read through an analog pin).


## Circuit
{{<gallery>}}
<img src="Power_Supply_1.jpg" class="grid-w50" />
<img src="Power_Supply_2.jpg" class="grid-w50" />

{{</gallery>}}

## Product
{{<gallery>}}
<img src="Power_1.jpg" class="grid-w50"/>
<img src="Power_2.jpg" class="grid-w50"/>
{{</gallery>}}


