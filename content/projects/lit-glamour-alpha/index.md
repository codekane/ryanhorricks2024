---
title: "Lit Glamour Alpha"
slug: "lit-glamour-alpha"
summary: "Lit Glamour Alpha pushed the boundaries of wearable tech, blending custom double-sided LED panels, advanced optical engineering, and sound-reactive features. This ambitious first phase laid the groundwork for scalable, innovative designs while overcoming challenges in power, weight, and usability."
date: "2023-07-18"
lastmod: "2025-01-20"
tags:
    - "Lit"
aliases:
    - "/portfolio/lit-glamour-alpha"
    - "/lit/lit-glamour-alpha"
    - "/portfolio/alpha"
    - "/lit/alpha"
---
**Project:** Lit Glamour Alpha  
**Role:** Founder and Developer  

{{<youtube qaizxUudKTc >}}

## Overview
**Lit Glamour Alpha** represents the ambitious beginning of a journey to create interactive, sound-reactive 
wearable technology. Inspired by a beloved hat that captivated everyone who wore it on New Year's Eve 2022, I 
set out to design, develop, and scale a product from a single prototype to a dozen units within six months. 
While the scope and challenges of the project proved far greater than anticipated, it laid the foundation for 
substantial innovation, iterative design, and technical mastery. The project’s core achievement was the 
completion of the **Alpha prototype**, featuring custom-designed, double-sided LED panels, advanced 
microcontroller electronics, and mmeticulous optical and power system system.

## Challenges and Objectives
- **Ambitious Scaling Goal:** Aiming to produce 12 units in 6 months while mastering new skills in optical engineering, electrical design, and fabrication.
- **Weight and Power Optimization:** Weight and Power Optimization: Reducing the weight of components and optimizing power consumption to improve wearability.
- **Custom Component Design:** Developing innovative LED panels and exploring advanced optical solutions to achieve a unique aesthetic.
- **Sound Reactivity:** Creating a dynamic, immersive user experience through audio-responsive lighting effects.

## My Contributions
### 1. Conceptualization and Prototyping
- **Initial Inspiration:** Derived from a hat built in 2019 that became a crowd favorite at events, inspiring the vision for a scalable, evolved product.
- Developed prototypes using the **ESP8266**, transitioning to the **ESP32-S3** for improved performmance and sound-reactive functionality.

### 2. Double-Sided LED Panel Design
- Designed **custom double-sided LED PCBs** in the shape of a heart to fit precisely with the hat’s structure, minimizing weight and unsightly wiring.
- Integrated LEDs in a zig-zag pattern to align with pre-drilled holes, enhancing both durability and aesthetics.

### 3. Optical Engineering and Casing Design
- Conducted **optical simulations** using FreeCAD’s Optics Workbench to model light output and evaluate the effects of various lens shapes.
- Designed multiple 3D-printable casings for resin casting, exploring advanced manufacturing techniques to enhance diffusion and light dispersion.
- Ultimately, developed a practical solution using epoxy to mount the LED panels directly to the hat. The epoxy served a dual purpose: securing the LEDs and acting as a light-diffusing lens.

### 4. Power System Development
- Iterated on power systems, integrating P-Channel Mosfets for safe switching and efficient power management.
- Integrated **P-Channel Mosfets** as relays to control power output to the LEDs, addressing the substantial quiscient current draw (~80mA total) when thte LEDs were ostensibly turned "off".
- Incorporated a Li-Ion charging circuit to enable safe and efficient recharging of the device’s battery, ensuring longevity and reliability.
- Selected and tested **LiPo batteries** in various form factors, optimizing for weight, capacity, and performance.
- Enhanced power system durability and reliability by incorporating safe switching mechanisms and minimizing unnecessary power consumption.

### 5. Open Source Collaboration and Firmware
- Leveraged the **Open Source WLED framework**, a powerful and feature-rich firmware, to save time on firmware development and focus on electronics and fabrication.
- Explored the **MoonModules branch of WLED** to unlock advanced features and hardware capabilities, pushing the performance limits of the system.
- Used **C++** to read and understand the WLED source code, including feature branches, allowing for precise customization and effective troubleshooting.
- Utilized **VSCode** and **PlatformIO** to configure and adapt WLED, ensuring compatibility and full functionality with custom hardware.

### 6. Iterative Design and Construction
- Progressed through multiple iterations of prototypes, refining designs to meet both aesthetic and functional goals.
- Sourced hats economically from suppliers based in China, modifying them to fit the project’s technical requirements.
- Addressed weight as a critical design factor by minimizing any excess material—wires were kept as short as possible while using an appropriate gauge (24ga) to reduce resistance at peak current.
- Substantially reduced voltage drop across the LED string by feeding power and ground to both ends, lowering the voltage drop from 0.17V to effectively 0.
- Integrated a set of **buttons** for brightness adjustment (+/-) and cycling through preset lighting patterns. While this feature added functionality, it proved to be somewhat unintuitive for users during testing.
- Utilized **leather punches** to customize hats, embedding LED panels seamlessly for a polished, professional finish.

## Outcomes and Results
- **Functional Alpha Prototype:** Delivered a sound-reactive wearable device featuring custom optical engineering, advanced power systems, and robust hardware.
- **Technical and Design Milestones:** Innovated with double-sided LED panels, epoxy-based light diffusion, and modular power systems, laying the groundwork for future iterations.
- **Lessons Learned:** Gained invaluable insights into the realities of scaling, technical complexity, and the iterative design process, all of which informed subsequent projects.

## Reflection
**Lit Glamour Alpha** pushed the boundaries of wearable technology and marked the beginning of my exploration 
into advanced hardware and optical engineering. While the original scope was ambitious, the journey provided 
invaluable lessons in balancing creativity with practicality. The project validated core technical concepts 
and set the stage for further innovation under the Lit brand.

## Technical Summary
- **Skills:** Optical Engineering, PCB Design, Electrical Engineering, Open Source Collaboration, Power Management, 3D Modeling (Rhino, FreeCAD)
- **Tools:** ESP8266, ESP32-S3, FreeCAD (Optics Workbench), EasyEDA, Rhino, Epoxy, Custom PCB Fabrication, WLED (including MoonModules), VSCode, PlatformIO, LiPo Batteries, Leather Punches
- **Key Features:** Double-Sided LED Panels, Optical Simulations, Open Source Integration (WLED), Dynamic Sound Reactivity, LiPo Battery and Charging System, Button Controls for Brightness and Pattern Cycling

## Gallery
### Inspiration
{{<gallery>}}
<img src="Original_Redux.jpg" class="grid-w50" />
<img src="Shambhala_2022_Hat_1.jpg" class="grid-w50" />
<img src="Shambhala_2022_Hat_2.jpg" class="grid-w50" />
<img src="Shambhala_2022_Hat_3.jpg" class="grid-w50" />
{{</gallery>}}


### Iteration 1
{{< youtube Zr0bHCgStcE >}}

{{<gallery>}}
<img src="ESP8266_Li-Ion_Charger_First_Iteration_Oops.JPG" class="grid-w50 md:grid-w33"/>
<img src="ESP8266_Buttons_MK1_Breadboard.JPG" class="grid-w50 md:grid-w33"/>
<img src="Cowboy_Prototype_MK1.JPG" class="grid-w50 md:grid-w33"/>
{{</gallery>}}

{{< youtube 4AJq0cm-uJs >}}

### Iteration 2

#### Double-Sided LED's
{{<gallery>}}
<img src="Heart_PCB_Schematic.JPG" class="grid-w50 md:grid-w33"/>
<img src="Lit_Glamour_Alpha.jpg" class="grid-w50 md:grid-w33"/>
<img src="Single_PCB_Palm.jpg" class="grid-w50 md:grid-w33"/>

{{</gallery>}}

#### Optical Simulations

{{<gallery>}}
<img src="Casing_Optics_Simulation_White.JPG" class="grid-w50" />
<img src="Casing_Optics_Simulation_Full_Spectrum.JPG" class="grid-w50" />
{{</gallery>}}

#### Breadboarding
{{<gallery>}}
<img src="Final_Countdown_Dual_Power_Supply.JPG" class="grid-w50" />
<img src="Final_Countdown_ESP32_S3_Breadboard.JPG" class="grid-w50" />
{{</gallery>}}

#### PCB Layout
{{<gallery>}}
<img src="pcb_layout/Alpha_S3_Schematic.JPG" class="grid-w50" />
<img src="pcb_layout/ESP32_S3_Board_Layout_Fail.JPG" class="grid-w50" />

{{</gallery>}}

#### Power Supply
{{<gallery>}}
<img src="power_supply/Updated_Power_Supply_1.jpg" class="grid-w50" />
<img src="power_supply/Updated_Power_Supply_2.jpg" class="grid-w50" />
{{</gallery>}}

#### Construction
{{<gallery>}}
<img src="construction/Epoxy_Embedded_PCB_1.jpg" class="grid-w50 md:grid-w33" />
<img src="construction/Epoxy_Embedded_PCB_2.jpg" class="grid-w50 md:grid-w33" />
<img src="construction/Epoxy_Embedded_PCB_3.jpg" class="grid-w50 md:grid-w33" />
{{</gallery>}}

#### Testing

{{< youtube LJVg5-wAMnY >}}
{{< youtube l4D51L7CRl8 >}}
{{< youtube VFhXBxQq73k >}}
{{< youtube Auu2c7Ahzgc >}}
