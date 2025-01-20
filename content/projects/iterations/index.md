---
title: "Iterations: Refining the Core Concept of Lit"
slug: "iterations"
summary: "A series of three prototypes, built to explore the limitations of my available hardware, test faculties for networked inter-connectivity, refine sub-systems, and to realize the core concept."
summary: "A series of three prototypes - based upon the ESP8266, ESP32-S2, and ESP32-S3. These were built to help me explore the limitations pertaining to processing power, refine the power supply/battery management system, and to provide me with enough devices to test out the faculties for commmunication between devices, to enable wireless synchronization, and ultimately enable me to realize the core concept behind this project."
date: "2023-12-05"
lastmod: "2025-01-20"
tags:
    - "Lit"
series: ["Lit"]
series_order: 2
aliases:
    - "/portfolio/esp32-s3-oled-led-controller/"
    - "/portfolio/esp32-s2-led-controller/"
    - "/portfolio/esp8266_split_rail_led_controller/"
    - "/portfolio/iterations"
    - "/lit/iterations"
---
**Project:** Lit  
**Role:** Founder and Hardware Developer  

<img src="cover.jpg" />

## Overview
**Iterations** is the second phase in the development of **Lit**, focused on creating and testing three 
prototypes based on the ESP8266, ESP32-S2, and ESP32-S3 microcontrollers. These prototypes explored hardware 
limitations, refined key subsystems, and tested wireless synchronization for sound-reactive lighting effects. 
Each iteration brought valuable insights into optimizing power systems, enhancing user interfaces, and 
advancing networked connectivity.

## Objectives and Challenges
- **Exploration of Hardware Limitations:** Evaluated the capabilities of the ESP8266, ESP32-S2, and ESP32-S3 for processing-intensive tasks, including audio signal processing, network synchronization, and real-time lighting effects.
- **Subsystem Refinement:** Enhanced physical user interfaces, transitioning from basic buttons and potentiometers to rotary encoders paired with OLED displays.
- **Power System Optimization:** Improved energy efficiency, reduced noise in power supplies, and enabled seamless operation on USB power with battery preservation.
- **Network Synchronization:** Made use of **UDP Multicast-based communication** to enable synchronized lighting effects across multiple devices.

## My Contributions
### 1. Prototyping and Design
- Developed three prototypes:
    - **ESP8266 Split Rail Controller:** Tested networked sound reactivity using experimental firmware that offloaded audio processing to other devices.
    - **ESP32-S2 Controller:** Incorporated a rotary encoder and I2S microphone for UI control and sound reactivity while evaluating its performance in audio processing. Found significant limitations in its capabilities compared to the S3.
    - **ESP32-S3 Controller:** Added an OLED display and I2S microphone for enhanced sound-reactive functionality and user interactivity.
- Designed and fabricated custom **adapter boards** for microcontrollers to simplify breadboarding and prototyping.

### 2. Exploration of Hardware Limitations
- Implemented experimental firmware to enable the ESP8266 to synchronize lighting effects with audio-reactive data processed on other devices.
- Conducted performance evaluations of the ESP32-S2 and ESP32-S3, identifying the latter as optimal for audio-intensive applications due to its dual-core architecture and advanced processing capabilities.

### 3. Subsystem Refinement
- Enhanced user interfaces across iterations:
    - Started with basic buttons and slide potentiometers.
    - Transitioned to a rotary encoder paired with an OLED display for intuitive, hardware-level control of brightness, effects, and color palettes.
- Tested and refined modular construction techniques to improve the reliability and maintainability of prototypes.

### 4. Power System Optimization
- Integrated a **USB Pass-Through Circuit** using P-Channel Mosfets and Schottky diodes, enabling simultaneous device operation and battery charging without impacting battery health.
- Reduced noise in the split-rail power supply with capacitors, achieving partial stability for the ESP8266. However, due to remaining instability, the design was eventually retired.
- Designed and tested efficient power delivery systems to support both analog and addressable LED systems, minimizing quiescent current draw and ensuring reliable performance.

### 5. Network Synchronization
- Leveraged **UDP Multicast-based communication** for wireless synchronization across devices, enabling real-time lighting effects.
- Experimented with using a Raspberry Pi Zero W as a dedicated router for managing network operations. This approach was abandoned due to insufficient processing power.

### 6. Practical Construction
- Used **JST-XH connectors** and custom protoboards to facilitate modular design and ease of assembly.
- Embedded LED panels seamlessly into enclosures, prioritizing aesthetics and accessibility for testing and maintenance.

## Outcomes and Learnings
- **Functional Prototypes:** Developed three unique controllers, each addressing specific challenges in power systems, network connectivity, and user interfaces.
- **Technical Validation:** Demonstrated the feasibility of sound-reactive, networked lighting systems while identifying limitations in certain hardware configurations.
- **Scalable Insights:** Gained a comprehensive understanding of modular design, power management, and network synchronization for future iterations.

## Technical Summary
- **Skills:** Microcontroller Integration, Power System Design, Sound Reactivity, Network Synchronization, Modular Prototyping
- **Tools:** ESP8266, ESP32-S2, ESP32-S3, EasyEDA, KiCad, JST-XH Connectors, FreeCAD, Logic Level Converters
- **Features:** Audio-Responsive Lighting, OLED UI, Split-Rail Power Supplies, Modular Construction, Wireless Synchronization

## Gallery

### ESP32-S3 LED Controller
<img src="cover.jpg" />
<img src="ESP32-S3/Case_OLED_Mockup.jpg" class="" />

#### Breadboard
{{<gallery>}}
<img src="ESP32-S3/Breadboarding.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S3/Breadboarding_2.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S3/Breadboarding_3.jpg" class="grid-w50 md:grid-w33" />
{{</gallery>}}


#### Layout
{{<gallery>}}
<img src="ESP32-S3/Protoboard_Ports_Mockup.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S3/Protoboard_Ports_Mockup_2.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S3/Protoboard_Ports_Mockup_3.jpg" class="grid-w50 md:grid-w33" />

{{</gallery>}}


#### Protoboard

{{<gallery>}}
<img src="ESP32-S3/OLED_PCB_Top.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S3/OLED_PCB_Bottom.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S3/OLED_PCB_Naked.jpg" class="grid-w50 md:grid-w33" />
{{</gallery>}}


#### Product
{{<gallery>}}
<img src="ESP32-S3/OLED_Encased_Off.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S3/OLED_Encased_Top.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S3/OLED_Encased_Side.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S3/OLED_Encased_Open.jpg" class="grid-w50 md:grid-w33" />
{{</gallery>}}



### ESP32-S2 LED Controller
Continuing with my experiments, and my penchant for using spare parts, I built another controller using the ESP32-S2. I equipped it with a rotary encoder, however my prime interest was in seeing how limited the S2 was compared to the S3, when being tasked with audio processing. The answer was quite - it did in fact work, however it came at the cost of UI responsiveness, with the web server often slowing to a crawl, and the audio processing time entering into the DANGER ZONE.
<img src="ESP32-S2/cover.jpg" />

#### Breadboarding
{{<gallery>}}
<img src="ESP32-S2/Lolin_S2_Mini.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S2/Breadboarding.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S2/Interface_Breadboard.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S2/Breadboard_Side_View.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S2/Breadboard_45_Degree_Angle.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S2/Breadboard_40_Degree_Angle.jpg" class="grid-w50 md:grid-w33" />
{{</gallery>}}

#### Assembly

{{<gallery>}}
<img src="ESP32-S2/S2_Mini_Protoboard.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S2/Case_With_Rotary_Encoder.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S2/Installed_In_Case.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S2/Installed_In_Case_Back_View.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP32-S2/Installed_In_Case_Top_View_Microphone.jpg" class="grid-w50 md:grid-w33" />
{{</gallery>}}

#### Power Pack
{{<gallery>}}
<img src="ESP32-S2/5000mAh_Power_Pack.jpg" class="grid-w50" />
{{</gallery>}}

#### Installation
{{<gallery>}}
<img src="ESP32-S2/Wall_Mount_Close_Up.jpg" class="grid-w50" />
<img src="ESP32-S2/Mounted_On_Wall.jpg" class="grid-w50" />
{{</gallery>}}

{{< youtube Rt7yyTXw4A8 >}}


### ESP8266 Split Rail LED Controller
Looking to experiment, I created another controller for a fixed installation using some parts I had lying around. It drives a single string of 5V addressable LED's, as well as a strip of analog 12V LED's, both being powered from either 5V USB pass-through, or a single Lithium Polymer Battery. What's more, using experimental firmware, I was able to have it sync to the audio reactive data from my other devices (without needing to do the processing itself).
<img src="ESP8266/cover.jpg" />

#### Breadboarding
{{<gallery>}}
<img src="ESP8266/Breadboard_Circuit.jpg" class="grid-w50" />
{{</gallery>}}

#### Power Supply

{{<gallery>}}
<img src="Split_Rail_Power_Supply_Front.jpg" class="grid-w50" />
<img src="Split_Rail_Power_Supply_Back.jpg" class="grid-w50" />
{{</gallery>}}

#### Noise
{{<youtube LyBV-9yD8q4 >}}


#### Mainboard
{{<gallery>}}
<img src="ESP8266/Analog_Controller.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP8266/Analog_Controller_2.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP8266/Split_Rail_Installed_In_Case.jpg" class="grid-w50 md:grid-w33" />
{{</gallery>}}

#### Installation
{{<gallery>}}
<img src="ESP8266/Split_Rail_Case.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP8266/Split_Rail_Demo.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP8266/Case_With_Cables.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP8266/Case_With_Cables_Side.jpg" class="grid-w50 md:grid-w33" />
<img src="ESP8266/Case_With_Cables_Back.jpg" class="grid-w50 md:grid-w33" />
{{</gallery>}}

### All-Together

#### Live Demo
{{<gallery>}}
<img src="live_demo/Live_Demo_S3_Mini_1.jpg" class="grid-w50" />
<img src="live_demo/Live_Demo_S3_Mini_2.jpg" class="grid-w50" />
<img src="live_demo/Live_Demo_S3_Mini_3.jpg" class="grid-w50" />
<img src="live_demo/Live_Demo_S3_Mini_4.jpg" class="grid-w50" />
{{</gallery>}}
{{<youtube TOupNLcAgPE >}}

#### Ensemble
{{<gallery>}}
<img src="ensemble/Hat_Plus_Ensemble.jpg" class="grid-w50 md:grid-w33" />
<img src="ensemble/Purple_Hat_Plus_Ensemble.jpg" class="grid-w50 md:grid-w33" />
<img src="ensemble/Red_Hat_Plus_Ensemble.jpg" class="grid-w50 md:grid-w33" />
<img src="ensemble/Sorting_Hat_Plus_Ensemble.jpg" class="grid-w50 md:grid-w33" />
<img src="ensemble/Dramatic_Hat_Plus_Ensemble.jpg" class="grid-w50 md:grid-w33" />
<img src="ensemble/Dramatic_Purple_Hat.jpg" class="grid-w50 md:grid-w33" />
<img src="ensemble/Illuminated_Hat_In_Profile.jpg" class="grid-w50 md:grid-w33" />
<img src="ensemble/Out_Of_Focus_Hat_Plus_Heart.jpg" class="grid-w50 md:grid-w33" />
{{</gallery>}}



