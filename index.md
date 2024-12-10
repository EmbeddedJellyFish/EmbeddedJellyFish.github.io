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
<summary>Table of Contents</summary>

<ul>
  <li><a href="#introduction">Introduction</a></li>
  <li><a href="#team-organization">Team Organization</a></li>
  <li><a href="#user-needs,-benchmarking-and-requirements">Benchmarking</a></li>
  <li><a href="#design-ideation">Design Ideation</a></li>
  <li><a href="#block-diagram">Block Diagram</a></li>
  <li><a href="#component-selection">Component Selection</a></li>
  <li><a href="#hardware-implementation">Hardware Proposal</a></li>
  <li><a href="#software-implementation">Software Proposal</a></li>
  <li><a href="#presentation-1">Presentation One</a></li>
</ul>
</details>

## <u>Introduction</u>

Weather stations are important to more people than just News Stations, as farmers, outdoor enthusiasts, and more rural communities rely heavily on weather predictions. Farmers need an accurate method of knowing weather conditions for crop timing and in Arizona, for droughts and temperature extremes. Many outdoor enthusiasts rely on weather forecasting for safe travel times and destinations, or determining resources for their trips. 

We are choosing to especially focus on a weather station that helps Arizona farmers. **In Arizona, the lack of accessible weather measurement systems limits the ability to monitor immediate local changes. While larger protocols operate effectively over oceanic areas, Arizona's enclosed geography presents a unique challenge.** As a secondary problem, Arizona farmers need to utilize every inch of land with purpose. **So we propose a mobile weather station that doesn't get in the way of their jobs, requires extra meteorological knowledge, or requires constant check-ins.**

## <u>Team Organization</u>

Team Charter - As a team we got together and thought about what we wanted our product to reflect for the team. It was decided that we want our teamwork and skills to be a part of our product since we are all passionate about engineering. The product will reflect our time management, team coordination, ideation, design, programming, and ability to put together a functional product.

Mission Statement - The goal of the product is to be a mobile weather station that accurately responds to environmental changes in real-time. This will be done over WiFi using the MQTT protocol which will help ensure seamless access to information.

[Team Charter](./team_organization.md)

## <u>User Needs, Benchmarking and Requirements</u>

**When developing a product we recognized the importance of researching user needs and requirements.** The team decided to take 5 similar products online and create a summary of user needs from documented feedback on the products. Then we grouped similar needs and ranked them both within their own group and in relation to each other. The most important product requirements fell under _Functionality_ and _Safety_ as we felt that the product must fulfill its purpose of existing and the product MUST be safe for users.

**Note:** The product will be assessed according to the requirements we detailed through team discussion, revisions, and testing. In the case a requirement is not met, revisions will be made to address it.

[Benchmarking and Requirements](./appendix.md)

## <u>Design Ideation</u>

We got together in person and had an informal discussion where people could communicate their ideas. Each group member was encouraged to give their ideas so everyone contributed. We found that this method worked best because when you are making ideas it is important to prevent yourself from filtering yourself too much so that you can all give your thoughts/iterate on that idea. We ranked ideas based on them fitting the requirements, their creativity and their practicality. Thanks to Skylar's excellent skills with computer sketching we were able to have a few visuals on potential ideas we discussed. 

[Process Breakdown](./appendix.md)

#### Selected Design
We selected the design based on the best combination of the ideas that the team came up with during the Design Ideation process. We went through a process of ruling out specifics that we did not want to include in any design iteration, and from there we developed 3 options. Based on application, creativity, and our requirements, we voted to develop our second design. Our second design was a small, toy boat that included a humidity sensor and a temperature sensor. 
<div align = "center">
    <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/CAD_Rendering.png">

</div>

## <u>Block Diagram</u>
>
Once we selected our design, we took turns discussing who would take ownership of which subsystem. From there, we did our own research into what kinds of parts we would need and what sort of signals would work best. Then we added it to the Block Diagram and one of the team members went back and made it look nice.
<div align = "center">
    <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Block_Diagram_V5.png">

</div>

## <u>Component Selection</u>
Similarly to how we decided which design we would use, we researched parts that would fulfill the requirements and chose three possibilities. Based on the written pros and cons, we then selected the best option with the exception of non-major components and the microcontroller. After those components were selected and we knew what kinds of signals our sensors and the motor driver would need, one of the team members followed the same process to determine the best microcontroller for our needs. After these were completed, we started adding the necessary materials to our Team Bill of Materials (BOM).

[Full Selection & Power Budget](./appendix.md)

#### Motor Driver (Actuator Subsystem)

| Solution 1 | Pros | Cons |
| ----- | ----- | ----- |
| <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Comp_Motor_Driver.png"> DRV8830DGQR $1.64 [Link](https://www.digikey.com/en/products/detail/texas-instruments/DRV8830DGQR/2520903)  | 3.6A peak output; Built-in fault protection; PWM control; Legs for easier soldering; Lowest price. | No built-in feedback control will require more coding; May require a heatsink to control overheating. |

#### Voltage Regulator (Micro-Controller Subsystem)

| Solution 3 | Pros | Cons |
| ----- | ----- | ----- |
| <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Comp_Volt_Reg.png"> LM2596DSADJR4G $2.70 [Link](https://www.digikey.com/en/products/detail/onsemi/LM2596DSADJR4G/2003291) |  Very high maximum output current of 3A; 90% efficiency; Switching at 150kHz; Has a high-voltage range |  Generates a lot of noise; Dropout voltage of 2-4V; Generates the most heat |

#### Humidity Sensor (Sensor 2 Subsystem)

| Solution 3 | Pros | Cons |
| ----- | ----- | ----- |
| <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Comp_Hum_Sen.png"> HIH6030-021-001 14.59$ [Link](https://www.digikey.com/en/products/detail/honeywell-sensing-and-productivity-solutions/HIH6030-021-001/4291625?_gl=1*gdce4m*_up*MQ..&gclid=Cj0KCQjw6oi4BhD1ARIsAL6pox2F7lC9dsWMuQcBle88dzdL_l3uBNudHsvwcUs5quX1dP1AyWQ45oEaAujNEALw_wcB) |  Humidity Range 0 \~ 100% RH; Accuracy ±2% RH; 1.62V \~ 5.5V; Can hand solder it; Big | Most expensive;  Operating range \-40°C \~ 105°C; 8 wires  |

#### Temperature Sensor (Sensor 1 Subsystem)

| Solution 3 | Pros | Cons |
| ----- | ----- | ----- |
| <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Comp_Temp_Sen.png"> TC74 $1.15 [Link](https://www.digikey.com/en/products/detail/microchip-technology/TC74A0-3-3VCTTR/443283)   | I2C; Lowest Price; Best Size; Experienced Soldering already | No application for an OpAmp; Accuracy varies by 3 degrees C; Not able to test new temperature sensor |

## <u>Hardware Implementation</u>

The Schematic below shows the design of a mobile weather station that can measure environmental conditions and sends the data back through Wi-Fi.

1. #### Temperature and Humidity Sensors
   The design includes a temperature sensor and a humidity sensor, which are needed for measuring environmental conditions. These sensors are connected to the microcontroller and provide real-time data on the air's temperature and moisture content, essential for weather monitoring.

2. #### Motor Driver and Motor
   The motor driver circuit controls the boat's motor, enabling movement across the water. The motor is used to move the boat along a GPS-defined path, which allows for data collection across different areas.

3. #### Mircrocontroller (PIC18F47K42T)
   The microcontroller processes inputs from the temperature and humidity sensors, controlling the motor driver for movement, and managing communication over Wi-Fi. 

4. #### Wi-Fi Communication (ESP 32)
   The schematic includes an ESP32 module for Wi-Fi communication, which allows the RC boat to upload the collected data to a server or cloud using the MQTT. Allowing the user to view weather conditions without being near the device.

5. #### Power
   The schematic includes a power supply system with a voltage regulator to keep stable power to the system. This power supply steps down 9 volts to 3.3 volts at 3.3 amps of current using an external battery for indepdenent operation of the boat.

For a more in depth look at the hardware here is the PCB and schematic: [Appendix - J: Hardware Implementation](./Appendix-J.md).

## <u>Software Implementation</u>

#### User Needs
&nbsp;&nbsp;&nbsp;&nbsp;The primary user need for this weather station is that it communicates accurate weather data (specifically from the temperature and humidity sensors) reliably and promptly. Users rely on this information to monitor and react to environmental conditions, often needing data to be transmitted without significant delays.

#### Product Requirements
&nbsp;&nbsp;&nbsp;&nbsp;The system continuously collects data from the temperature and humidity sensors, which are then communicated to the central processing unit using UART. These readings are processed and transmitted to the internet over Wi-Fi using the MQTT protocol. The MQTT protocol ensures that messages (temperature and humidity data) are sent efficiently with minimal delay, meeting the user's need for timely data communication. As a lightweight messaging protocol, MQTT is particularly effective for real-time environmental monitoring systems, ensuring that updates are received reliably and without unnecessary latency.

&nbsp;&nbsp;&nbsp;&nbsp;The rain sensor measures precipitation levels and communicates this data via UART to the main processor. If the system detects light rain or sprinkling (based on predefined thresholds), it will trigger a timely alert through the MQTT protocol. These alerts notify users of environmental changes, such as the onset of rain, and could prompt actions such as turning off sprinklers or activating drainage systems. The communications subsystem prioritizes accuracy and timeliness, ensuring that these alerts are both precise (accurate rain measurements) and immediate, which is particularly useful for users relying on weather data for irrigation or similar applications.The system is designed to handle only environmental data, which is non-personal. This satisfies both the product requirement for privacy and security and the user need for a system that does not collect or store personal information. The design choices regarding data communication and storage reflect a conscious effort to avoid privacy concerns, ensuring compliance with data protection standards.

For more insight into our software devlopment process go to [Appendix I: Software Explored](./Appendix-I.md)

## <u>Presentation 1</u>
[Presentation](./presentation.md)
