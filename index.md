---
layout: default
title: SeaScout
---
# Project SeaScout
Arizona State Univeristy, EGR314, Nichols
Team 306
August 30, 2024

Contributers:
Harris Bokhari,
Skyler Riley,
Kai-ra de la Fuente,
Connor Bogenn

<details>
    
<summary> Table of Contents </summary>
    
[Introduction](#introduction)

[Team Organization](#team-organization)

[Benchmarking](#user-needs,-benchmarking-and-requirements)

[Design Ideation](#design-ideation)

[Block Diagram](#block-diagram)

[Component Selection](#component-selection)

[Hardware Proposal](#hardware-proposal)

[Software Proposal](#software-proposal) 
    
</details>

## Introduction

Weather stations are important to more people than just News Stations, as farmers, outdoor enthusiasts, and more rural communities rely heavily on weather predictions. Farmers need an accurate method of knowing weather conditions for crop timing and in Arizona, for droughts and temperature extremes. Many outdoor enthusiasts rely on weather forecasting for safe travel times and destinations, or determining resources for their trips. 

We are choosing to especially focus on a weather station that helps Arizona farmers. **In Arizona, the lack of accessible weather measurement systems limits the ability to monitor immediate local changes. While larger protocols operate effectively over oceanic areas, Arizona's enclosed geography presents a unique challenge.** As a secondary problem, Arizona farmers need to utilize every inch of land with purpose. **So we propose a mobile weather station that doesn't get in the way of their jobs, requires extra meteorological knowledge, or requires constant check-ins.**

##  Team Organization

Team Charter - As a team we got together and thought about what we wanted our product to reflect for the team. It was decided that we want our teamwork and skills to be a part of our product since we are all passionate about engineering. The product will reflect our time management, team coordination, ideation, design, programming, and ability to put together a functional product.

Mission Statement - The goal of the product is to be a mobile weather station that accurately responds to environmental changes in real-time. This will be done over WiFi using the MQTT protocol which will help ensure seamless access to information.

[Team Charter](./team_organization.md)

## User Needs, Benchmarking and Requirements

\note
The product will be assessed according to the requirements we detailed through team discussion, revisions, and testing. In the case a requirement is not met, revisions will be made to address it.

**When developing a product we recognized the importance of researching user needs and requirements.** The team decided to take 5 similar products online and create a summary of user needs from documented feedback on the products. Then we grouped similar needs and ranked them both within their own group and in relation to each other. The most important product requirements fell under _Functionality_ and _Safety_ as we felt that the product must fulfill its purpose of existing and the product MUST be safe for users.

[Benchmarking and Requirements](./appendix.md)

## Design Ideation

We got together in person and had an informal discussion where people could communicate their ideas. Each group member was encouraged to give their ideas so everyone contributed. We found that this method worked best because when you are making ideas it is important to prevent yourself from filtering yourself too much so that you can all give your thoughts/iterate on that idea. We ranked ideas based on them fitting the requirements, their creativity and their practicality. Thanks to Skylar's excellent skills with computer sketching we were able to have a few visuals on potential ideas we discussed. 

[Process Breakdown](./appendix.md)

### Selected Design
We selected the design based on the best combination of the ideas that the team came up with during the Design Ideation process. We went through a process of ruling out specifics that we did not want to include in any design iteration, and from there we developed 3 options. Based on application, creativity, and our requirements, we voted to develop our second design. Our second design was a small, toy boat that included a humidity sensor and a temperature sensor. 
<div align = "center">
    <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/CAD_Rendering.png">

</div>

## Block Diagram
Once we selected our design, we took turns discussing who would take ownership of which subsystem. From there, we did our own research into what kinds of parts we would need and what sort of signals would work best. Then we added it to the Block Diagram and one of the team members went back and made it look nice.
<div align = "center">
    <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Block_Diagram.png">

</div>

## Component Selection
Similarly to how we decided which design we would use, we researched parts that would fulfill the requirements and chose three possibilities. Based on the written pros and cons, we then selected the best option with the exception of non-major components and the microcontroller. After those components were selected and we knew what kinds of signals our sensors and the motor driver would need, one of the team members followed the same process to determine the best microcontroller for our needs. After these were completed, we started adding the necessary materials to our Team Bill of Materials (BOM).

[Full Selection & Power Budget](./appendix.md)
### Motor Driver

<div align = "center">
    <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Component_Motor_Driver.png">

</div>

### Voltage Regulator

<div align = "center">
    <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Component_Volt_Reg.png">

</div>

### Humidity Sensor

<div align = "center">
    <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Component_Humidity_Sensor.png">

</div>

### Temperature Sensor

<div align = "center">
    <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Component_Temp_Sensor.png">

</div>

## Hardware Proposal
![Schematic](https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Schematic.png)
[See More](./appendix.md)

## Software Proposal
![Software Diagram](https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Software_Diagram.png)

## Presentation 1
[Presentation](./presentation.md)
