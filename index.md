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

# Table of Contents
| Description            | Link                      |
|------------------------|---------------------------|
| Project Introduction    | [Introduction](#introduction) |
| Team Organization       | [Team Org](#team-organization) |


## Introduction
Weather stations are important to more people than just News Stations, as farmers, outdoor enthusiasts, and more rural communities rely heavily on weather predictions. Farmers need an accurate method of knowing weather conditions for crop timing and in Arizona, they rely on weather stations to know when they should compensate for lack of natural rain. Many outdoor enthusiasts rely on weather forecasting to know when they can safely travel to certain areas or when they should pack extra resources for their trips. The main limitations to current designs are their positioning and accuracy for rain measurements with many customers struggling to find the perfect location for data collection or setting up the weather station in a secure location. Most designs can support wireless data transfer over WiFi so this iteration would need to maintain that along with the accuracy of readings.

##  Team Organization

Team Charter - As a team we got together and thought about what we wanted our product to reflect for the team. It was decided that we want our teamwork and skills to be a part of our product since we are all passionate about engineering. The product will reflect our time management, team coordination, ideation, design, programming, and ability to put together a functional product.

Mission Statement - The goal of the product is to be a mobile weather station that accurately responds to environmental changes in real-time. This will be done over WiFi using the MQTT protocol which will help ensure seamless access to information.
[See More](./team_organization.md)

## User Needs, Benchmarking and Requirements

When developing a product we recognized the importance of researching user needs and requirements. The team decided to take 5 similar products online and create a list of user needs and requirements. At first, it was written down without any organization or formatting but as the process continued we grouped similar needs together, ranked user needs based on importance, and then categorized them into groups. The team felt that the most important product requirements are functionality and safety; one of our team members said that the product must fulfill its purpose of existing and the product MUST be safe for users which is a good justification for ranking the importance the way we did. The product will be assessed according to the requirements we detailed through team discussion, revisions, and testing. In the case a requirement is not met, revisions will be made to address it.
[See More](./appendix.md)

## Design Ideation

We got together in person and had an informal discussion where people could communicate their ideas. Each group member was encouraged to give their ideas so everyone contributed. We found that this method worked best because when you are making ideas it is important to prevent yourself from filtering yourself too much so that you can all give your thoughts/iterate on that idea. We ranked ideas based on them fitting the requirements, their creativity and their practicality. Thanks to Skylar's excellent skills with computer sketching we were able to have a few visuals on potential ideas we discussed. 
[See More](./appendix.md)

### Selected Design
We selected the design based on the best combination of the ideas that the team came up with during the Design Ideation process. We went through a process of ruling out specifics that we did not want to include in any design iteration, and from there we developed 3 options. Based on application, creativity, and our requirements, we voted to develop our second design. Our second design was a small, toy boat that included a humidity sensor and a temperature sensor. 

## Block Diagram
Once we selected our design, we took turns discussing who would take ownership of which subsystem. From there, we did our own research into what kinds of parts we would need and what sort of signals would work best. Then we added it to the Block Diagram and one of the team members went back and made it look nice.
![Block Diagram](https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Block_Diagram.png)

## Component Selection
Similarly to how we decided which design we would use, we researched parts that would fulfill the requirements and chose three possibilities. Based on the written pros and cons, we then selected the best option with the exception of non-major components and the microcontroller. After those components were selected and we knew what kinds of signals our sensors and the motor driver would need, one of the team members followed the same process to determine the best microcontroller for our needs. After these were completed, we started adding the necessary materials to our Team Bill of Materials (BOM).
<iframe src="docs/Component_Selection.pdf" width="100%" height="600px">
    This browser does not support PDFs. Please download the PDF to view it: <a href="docs/Component_Selection.pdf">Download PDF</a>
</iframe>

<iframe src="docs/Microcontroller_Selection.pdf" width="100%" height="600px">
    This browser does not support PDFs. Please download the PDF to view it: <a href="docs/Microcontroller_Selection.pdf">Download PDF</a>
</iframe>

## Hardware Proposal
![Schematic](https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Schematic.png)
[See More](./appendix.md)

## Software Proposal
![Software Diagram](https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Software_Diagram.png)

## Presentation 1
[Presentation](./presentation.md)
