---
title: "Pharmacokinetics"
slug: "pharmacokinetics"
summary: "Pharmacokinetics is a desktop app designed to estimate plasma drug concentrations using dosage history and pharmacokinetic data. Built with an Angular/Electron front-end and a Django back-end, the app supports complex scenarios like extended-release formulations and has provided both technical learning and personal growth opportunities."
date: "2022-11-22"
lastmod: "2025-01-16"
aliases:
    - "/portfolio/pharmacokinetics"
---
**Projects:** Pharmacokinetics - Plasma Concentration Estimation Tool  
**Role:** Solo Developer

## Overview
Pharmacokinetics is a personal project inspired by my work at The MARA Group, designed to estimate the 
plasma concentration of a drug over time. This desktop app combines an **Angular/Electron** front-end with a 
**Python/Django** back-end (after an experimental version in **Go**). The tool allows users to input dosage 
histories and pharmacokinetic data to generate pseudo-accurate blood level projections. Beyond its technical 
aspects, this project served as a deeply personal exploration of data visualization, health, and recovery.

## Challenges and Objectives
- **Plasma Concentration Estimation:** Creating a tool to visualize and analyze drug blood levels over time based on dosage history and pharmacokinetic properties.
- **Iterative Development Process:** Experimenting with different back-end frameworks (Go, FastAPI, Django) to optimize functionality and development speed.
- **Custom User Interface:** Building an intuitive, data-driven desktop application using Angular and Electron.
- **Accuracy and Flexibility:** Supporting complex pharmacokinetic scenarios, including extended-release formulations and multiple routes of administration.

## My Contributions

### 1. Front-End Development
- Designed and developed a **web app** using **Angular**, later packaged as a desktop application with **Electron** for cross-platform compatibility.
- Integrated dynamic charting functionality to visualize dosage history and estimated blood levels, using APIs to pull data from the back-end.
- Added features for adjusting date ranges and graph scales to improve usability and performance.

### 2. Back-End Development
- **Version 1 (Go):** Built an initial prototype in Go to learn the language and create a foundation for the project. While functional, it proved slow for iterative development.
- **Version 2 (Python/Django):** Rebuilt the back-end using **Django**, leveraging its admin panel for data entry (e.g., substances, formulations, and pharmacokinetics).
    - Used **Django Rest Framework** (DRF) to build APIs for front-end integration.
    - Implemented data models for extended-release formulations, bioavailability by route, and dose history tracking.

### 3. Pharmacokinetic Customizations
- Enabled support for complex scenarios, such as extended-release formulations (e.g., Dexedrine XR) and variable bioavailability by route of administration.
- Added features for handling edge cases like Daylight Saving Time (DST) issues and month transitions in date handling.

### 4. Personal Impact and Data Visualization
- Designed the app to provide insights into personal behavior patterns related to medication use.
- Used the data to visualize trends in my own medication use, ultimately aiding in recovery and fostering self-awareness.

## Outcomes and Results
- **Functional Prototype:** Delivered a desktop app capable of estimating plasma concentration based on dosage history and pharmacokinetics.
- **Iterative Development Success:** Gained valuable experience with multiple back-end frameworks, settling on Django for speed and flexibility.
- **Personal Insights:** Used the app as a tool for self-reflection, contributing to long-term recovery and lifestyle changes.

## Reflection
This project taught me the value of iterative design, adaptability, and leveraging the right tools for the 
job. While initially inspired by professional work, Pharmacokinetics became a deeply personal endeavor, 
blending my technical skills with my commitment to growth and recovery. Building this tool reinforced my 
belief in the power of software to drive meaningful change, both personally and professionally.

## Technical Summary
- **Skills:** Front-End Development, Back-End Development, Data Visualization, Pharmacokinetics Modeling
- **Tools:** Angular, Electron, Python, Django, Django Rest Framework, Go
- **Specialized Tasks:** Charting Integration, API Development, Pharmacokinetics Modeling, Data Visualization

## Gallery

### Front End
{{<github repo="codekane/bloodlevel" >}}

{{<gallery>}}
<img src="electron-app-1.png" class="grid-w50 md:grid-w33" />
<img src="electron-app-2.png" class="grid-w50 md:grid-w33" />
<img src="electron-app-3.png" class="grid-w50 md:grid-w33" />
<img src="electron-app-4.png" class="grid-w50 md:grid-w33" />
<img src="electron-app-5.png" class="grid-w50 md:grid-w33" />
{{</gallery>}}

### Back End

#### Version 1
{{<github repo="codekane/go-bloodlevel" >}}

#### Version 2
{{< github repo="codekane/Pharmacokinetics" >}}

{{<gallery>}}
<img src="add-substance.png" class="grid-w50" />
<img src="add-dosage-form.png" class="grid-w50" />
{{</gallery>}}

