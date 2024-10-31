---
title: "3000 mAh Power Pack"
date: 2024-06-06
summary: "A much smaller, lighter source of power than my previous devives. It uses a TP4056 module for charging, together with a couple of mosfets, and a zener diode to enable USB-Passthrough. This has proven safe, yet without voltage regulation I've encountered instabilities (and data corruption), so this is as much about what's been done well, as what must be done better."
lastmod: "2024-11-01"
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
- (1) [1N5817 Zener Diode](https://www.amazon.ca/dp/B07CJMBMJS?ref=ppx_yo2ov_dt_b_fed_asin_title). This is used to shunt 5V USB power into the system, taking priority over the battery power, when it's available.
- (1) SPDT Switch. I scavenged this from a AA-Powered light string I got at the dollar store.
- (2) 10k Ohm Pull-Up/Down Resistors. These are connected to the gate of the P-Channel Mosfets, pulling them down unless power from elsewhere in the circuit is provided to overwhelm the minimal flow provided through the resistor.
- (2) 100k Ohm Resistors. These are used to create a voltage divider, so as to make the peak 4.2V battery voltage possible to read from a 3.3V analog pin on the microcontroller.
- (1) 2-pin JST-XH Connector. This is used to provide a solid, detachable connection between the board, and the battery.
- (1) 6-pin JST-XH Connector. I don't actually need all six pins here. I'm using two for ground, one for switched battery voltage, and one for always-on battery voltage (value divided by two, to be read through an analog pin).


## Circuit
{{<gallery>}}
<img src="Power_Supply_1.jpg" class="grid-w50" />
<img src="Power_Supply_2.jpg" class="grid-w50" />
{{</gallery>}}

The circuit, as designed is, intended to fit in a very small form factor (at least, given the use of through-hole components).

The way it works is as such:

Battery is connected to the 2-pin JST-XH connector. This routes to the B+ and B- connecetions on the TP4056.

TP 4056 USB + connecetion is routed through the 1N5817 Zener Diode to the gate of the first Mosfet. The gate is 
also pulled down to ground (meaning, because it's a P-Channel mosfet, it will only open in the event that the gate has been 
pulled down to ground. Because the pull-down resistor is quite large, when their is active USB power, it will be pulled high, and thus inactive. 

The source on the first mosfet is connected to the positive output from the TP4056. This provides low-voltage protection for the battery (keeping it safe). 
In the event that their is no USB power connected, the gate of this mosfet will be pulled to grain, meaning that the battery voltage is able to flow from the 
source, through to the drain. If their is USB power, then this is prevented.

The output from the Zener Diode is connceted to the drain of the first mosfet. Because it's a diode, in the vent that there is no USB power, the battery power 
that flows is prevented from flowing backwards into the TP4056 (in any meaningful quantity, at least).

The drain from this first mosfet is then run into the source of the 2nd mosfet. The gate for this mosfet is connected to the middle terminal of the SPDT switch. 
One of the other terminals is then connected to ground, while the other can either be connected to positive, or else left disconnected, with the middle terminal instead 
being connected to a pull-up resistor.

The drain of this 2nd mosfet is the connected to the + pin of the 6-pin JST-XH header. I've also connected the OUT+ from the TP4056 to another pin on this header, routing it through a 
voltage divider to divide the output voltage in half (for measuring purposes). The other two connected pins are both Ground, and Ground is not being switched, so these will always be conneected.
## Case
{{<gallery>}}
<img src="Power_1.jpg" class="grid-w50"/>
<img src="Power_2.jpg" class="grid-w50"/>
{{</gallery>}}

I did put some work into designing a case to be 3D-Printed for this project, however I never actually got around to it. 
Honestly, that took a lot of time, and though I did actually produce a design with the suitable dimensions (and also an articulating piece to slide in/out, and thus enable 
servicing the device), it was far simpler, when the need came to put this into the field, to simply wrap it in electrical tape.

I first used electrical tape around the PCB, to eliminate any sharp, pointy edges that might harm the battery, 
and then I wrapped the entire case in electrical tape. I connecteede the JST-Xh cable, and again, wrapped it all in tape. 

As it stands, it looks quite similar to some commercial battery packs that I've seen, and weight-wise, this is a far superior option 
to my prior go-to for battery boxes: joint tins. Cute as they may be, weight was a concern for this build, and I Feel I made the right choice.

Care was taken to ensure that the SPDT switch was still accessable, despite the tape sarcophagus.

## Lessons

One problem with this build was actually to do with phantom power draw. Even when switched off, for long periods of time, 
I found that the battery was draining to a degree faster than might be expected to be caused by the Lithium-Polymer batteries self-discharge.

I haven't gotten to the bottom of that, however in the process of writing this up, I've realized that the pull up/down reseistors may be to blame.

Additionally, there's the voltage divider for the battery voltage sensor. That isn't gated behind the power switch, and so if there's any current leaking through that at all, 
even if it's 1mA, multiply that by hours and days, and you wind up with a veery substantial draw.

Additionally, I've found an increasing need for regulated voltage, and for this reason, in future versions of this device I'm inclinede to investigate the implemntation of a 
5V switched-mode converter. I'd been doing without, because, at least in theory, I was able to get good mileage out of the straight battery voltage for powering the 5V LED's. 
The problem hasn't been with them, but rather with the microprocessor, and the LDO regulator included upon it. Once the voltrage from the battery drops too low, the regulator is 
no longer able to provide a consistent 3.3V (and this is a big problem). I'd like to maintain access to the straight battery voltage, however I'd like to include a regulated 5V 
(or perhaps even 3.3V, although this is questionable).

In the future, I think that the voltage divider for current sensing can live on another board, and I'd like to have both the 
5V and battery voltage gated behind the power switch.

I'd also like to experiment with alternatives to the SPDT switch for controls. I found that it was liable to turn off/on when jostled in the field. 
Implementing a soft power switch, along the lines of what you get on a PC, is a solution that comes to mind. This would require an additional circuit making use of capacitors, 
enabling a single button press to turn on, and then a long press to turn off. This long press could also be translated into some form of digital signal that passes into the 
microprocessor, to help ensure a clean shut down (and avoid data corruption).
