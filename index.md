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
    
- [Introduction](#introduction)
- [Team Organization](#team-organization)
- [Benchmarking](#user-needs,-benchmarking-and-requirements)
- [Design Ideation](#design-ideation)
- [Block Diagram](#block-diagram)
- [Component Selection](#component-selection)
- [Hardware Proposal](#hardware-implementation)
- [Software Proposal](#software-implementation)
- [Presentation One](#presentation-1)
    
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

### Motor Driver (Actuator Subsystem)

| Solution 1 | Pros | Cons |
| ----- | ----- | ----- |
| <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Comp_Motor_Driver.png"> DRV8830DGQR $1.64 [Link](https://www.digikey.com/en/products/detail/texas-instruments/DRV8830DGQR/2520903)  | 3.6A peak output; Built-in fault protection; PWM control; Legs for easier soldering; Lowest price. | No built-in feedback control will require more coding; May require a heatsink to control overheating. |

### Voltage Regulator (Micro-Controller Subsystem)

| Solution 3 | Pros | Cons |
| ----- | ----- | ----- |
| <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Comp_Volt_Reg.png"> LM2596DSADJR4G $2.70 [Link](https://www.digikey.com/en/products/detail/onsemi/LM2596DSADJR4G/2003291) |  Very high maximum output current of 3A; 90% efficiency; Switching at 150kHz; Has a high-voltage range |  Generates a lot of noise; Dropout voltage of 2-4V; Generates the most heat |

### Humidity Sensor (Sensor 2 Subsystem)

| Solution 3 | Pros | Cons |
| ----- | ----- | ----- |
| <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Comp_Hum_Sen.png"> HIH6030-021-001 14.59$ [Link](https://www.digikey.com/en/products/detail/honeywell-sensing-and-productivity-solutions/HIH6030-021-001/4291625?_gl=1*gdce4m*_up*MQ..&gclid=Cj0KCQjw6oi4BhD1ARIsAL6pox2F7lC9dsWMuQcBle88dzdL_l3uBNudHsvwcUs5quX1dP1AyWQ45oEaAujNEALw_wcB) |  Humidity Range 0 \~ 100% RH; Accuracy ±2% RH; 1.62V \~ 5.5V; Can hand solder it; Big | Most expensive;  Operating range \-40°C \~ 105°C; 8 wires  |

### Temperature Sensor (Sensor 1 Subsystem)

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

#### Process
&nbsp;&nbsp;&nbsp;&nbspWe started with the most basic version of what our design would do, which consisted of the microcontroller reading and displaying the data from the sensors. From there we developed the actuator subsystem and designed it so that there would be a cycle of the motors turning on and off based on where the user desired the boat to go. Then we added aspects that would satisfy user interface needs such as allowing the user to choose what route the boat should follow and displaying the data in a user-friendly manner. A lot of this was done on a one-on-one basis where the original creator of the UML would discuss the desires of the owner of that subsystem and then translate that into a program diagram. 

#### Changes
The following are the top 5 biggest changes to our software design since the original proposal. 

1. ##### Updated flow and interrupts to include a time delay to prevent data overwrite. 
   Originally, the system was designed to collect and process data from various sensors at a constant rate without any time delay. This could result in data overwriting where new data would overwrite old data before it was fully processed. To fix this, we added a time delay in the flow of data collection, which ensures that each data point has adequate time for processing and transmission before the next one is collected. This change ensures that data overwriting is prevented, and the system handles sensor data in a controlled and orderly manner.

2. ##### Updated aesthetics for readability purposes. 
   Initially, the UML diagram had elements that were visually cluttered, making it difficult to quickly understand the flow of data or the interactions between different subsystems. The layout did not optimize space, and key components were difficult to distinguish during presentations. So we updated the aesthetics by reorganizing elements, reducing visual clutter, and creating more space between subsystems for better clarity. I also ensured that line styles were used effectively to differentiate between various types of interactions and increased font size.

3. ##### Removed unnecessary nested loops and interlocking loops.
   The original design included nested loops and interlocking loops in the system's process flow, which made the logic unnecessarily complex. These loops were creating inefficiencies in the system, potentially leading to unwanted delays or unpredictable behavior due to the system getting stuck in complex cycles. So we refactored the diagram by eliminating redundant loops and simplifying the flow of operations. Instead of using nested or interlocking loops, we streamlined the logic by creating clearer decision paths and using sequential steps where possible. This change made it so the system can now process tasks in a more linear, predictable manner without getting slowed down by unnecessary cycles.

4. ##### Added outputs and inputs for the various subsystems.
   Initially, some of the subsystems were not clearly defined with explicit inputs and outputs. This made it unclear how data was being passed between subsystems and where information was coming from or going. It was difficult to track the flow of data and understand the interdependencies between different system components. To fix this, we added explicit inputs and outputs to each subsystem in the diagram to clarify how data flows between them. These changes help visualize the system's data flow and improve the understanding of how each component interacts with others.

5. ##### Changed motion delays to account for the time it takes for the boat to move between positions and complete a cycle. 
   The original motion delays in the system did not take into account the actual time required for the boat to physically move between positions and complete its cycle. This could lead to inaccurate timing or premature actions, as the system might attempt to act before the boat has completed its current task or reached the correct position. To resolve this, we modified the motion delays to account for the actual time it takes for the boat to move between its positions. This involved adjusting the timing parameters and ensuring that delays were introduced in the process flow so that the boat had adequate time to complete its movement and return to a stationary state before the next cycle began. This change improves the synchronization between the boat’s movements and the system’s actions, preventing errors and ensuring the system works smoothly and predictably during each cycle.

#### Version 2.0
&nbsp;&nbsp;&nbsp;&nbsp;In creating a Version 2.0 of the software design, we would focus on several key areas of improvement: enhancing system reliability, simplifying code for better maintainability and debuggability, and optimizing data flow and communication protocols. The updated design would aim to create a more robust, efficient, and scalable system that can handle future growth and integration with additional features or sensors.
&nbsp;&nbsp;&nbsp;&nbsp;To improve reliability and stability, we would incorporate redundancy mechanisms for critical subsystems, such as sensor data acquisition and data transmission. For example, adding error-checking routines and data validation would prevent the system from acting on corrupted or inaccurate sensor readings. Implementing watchdog timers would also help prevent the system from freezing or entering into infinite loops due to unforeseen conditions. Additionally, we could consider implementing a fall-back protocol in case of failures in communication such as WiFi failure resulting in the use of a temporary local storage and periodic attempts to reconnect. This change would make the system more resilient in real-world operating conditions.
&nbsp;&nbsp;&nbsp;&nbsp;One of the most significant improvements we would focus on is making the code more modular and easier to debug. In Version 1.0, the system has large monolithic functions and tightly coupled code, which can make it difficult to isolate issues during testing. In Version 2.0, we would refactor the software into more modular, function-based components. This refactoring would also make the system easier to update in the future by allowing us to add new sensors or peripherals with minimal disruption to other parts of the code. For example, if a new motion sensor was added, it could be implemented as a new module without changing the core logic of the system. 
&nbsp;&nbsp;&nbsp;&nbsp;To optimize the communication protocols, we would focus on improving the efficiency of data transmission and making it more robust. In Version 1.0, the system uses MQTT over Wi-Fi to transmit data. While this is an efficient protocol, we would consider incorporating data compression techniques to reduce bandwidth usage, especially if the system is expected to handle large amounts of sensor data.
&nbsp;&nbsp;&nbsp;&nbsp;Additionally, we would implement error-checking mechanisms like checksum validation for each data packet sent via MQTT to ensure data integrity. If a packet is corrupted during transmission, the system would be able to request a retransmission without losing critical information.
I would update the flow diagram to include: Modular components that clearly show the separation of tasks (e.g., sensor reading, data processing, actuation).
Redundancy and error handling, including decision points for retrying failed operations (e.g., lost communication or sensor errors).
New peripherals, like real-time clocks and encoders, are integrated into the system with clear communication protocols (I2C/SPI).
More robust communication, including data validation, error checking, and QoS adjustments in the MQTT transmission.


## <u>Presentation 1</u>
[Presentation](./presentation.md)
