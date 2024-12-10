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
  <li><a href="#user-needs-and-benchmarking">Benchmarking</a></li>
  <li><a href="#product-requirements">Product Requirements</a></li>
  <li><a href="#design-ideation">Design Ideation</a></li>
  <li><a href="#block-diagram">Block Diagram</a></li>
  <li><a href="#component-selection">Component Selection</a></li>
  <li><a href="#hardware-implementation">Hardware Proposal</a></li>
  <li><a href="#software-implementation">Software Proposal</a></li>
  <li><a href="#presentation-1">Presentation One</a></li>
  <li><a href="#system-verification">System Verification</a></li>
  <li><a href="#lessons-learned">Lessons Learned</a></li>
  <li><a href="#recommendations">Recommendations</a></li>
</ul>
</details>

## <u>Introduction</u>

Weather stations are important to more people than just News Stations, as farmers, outdoor enthusiasts, and more rural communities rely heavily on weather predictions. Farmers need an accurate method of knowing weather conditions for crop timing and in Arizona, for droughts and temperature extremes. Many outdoor enthusiasts rely on weather forecasting for safe travel times and destinations, or determining resources for their trips. 

We are choosing to especially focus on a weather station that helps Arizona farmers. **In Arizona, the lack of accessible weather measurement systems limits the ability to monitor immediate local changes. While larger protocols operate effectively over oceanic areas, Arizona's enclosed geography presents a unique challenge.** As a secondary problem, Arizona farmers need to utilize every inch of land with purpose. **So we propose a mobile weather station that doesn't get in the way of their jobs, requires extra meteorological knowledge, or requires constant check-ins.**

## <u>Team Organization</u>

Team Charter - As a team we got together and thought about what we wanted our product to reflect for the team. It was decided that we want our teamwork and skills to be a part of our product since we are all passionate about engineering. The product will reflect our time management, team coordination, ideation, design, programming, and ability to put together a functional product.

Mission Statement - The goal of the product is to be a mobile weather station that accurately responds to environmental changes in real-time. This will be done over WiFi using the MQTT protocol which will help ensure seamless access to information.

[Team Charter](./team_organization.md)

## <u>User Needs and Benchmarking</u>

**When developing a product we recognized the importance of researching user needs and requirements.** The team decided to take 5 similar products online and create a summary of user needs from documented feedback on the products. Then we grouped similar needs and ranked them both within their group and concerning each other. The most important product requirements fell under _Functionality_ and _Safety_ as we felt that the product must fulfill its purpose of existing and the product MUST be safe for users.
After finishing the product some changes we would make to our initial user needs and benchmarking is looking more into how other devices that are made to be on water deal with measuring humidity and keeping everything watertight for the electronics. Shifting more into looking into more specific weather sensors for use on water than general consumer sensors that can go anywhere.

See a full document regarding our benchmarking in [Appendix B](./appendix.md).

## <u>Product Requirements</u>

The following is a small sample of our product requirements, see more in [Appendix C](./appendix.md).
_Aspects_
1. ### Functionality - 
    1.1 The system shall respond to the environment using serial sensing and actuation for a mobile weather station.
    1.2 The system shall broadcast the environmental data to the internet over WiFi using the MQTT protocol. 
        1.2.1 The device should utilize non-personal applications for read/write functionalities.
        1.2.2 The device should have a long range of over 10 meters.
    1.3 Main communication between subsystems shall be completed using UART.
    1.4 The device will utilize a 16-bit Microchip PIC family.
    1.5 This project will utilize C (MPLAB X) and Visual Studio Code.
    1.6 The digital gauge shall accurately communicate measurements.
    1.7 The communications subsystem shall prioritize accuracy and timely alerts in relation to rain measurements by focusing on sprinkling or light rain applications.
    1.8 The communications subsystem should prioritize readability in the visual representation of the data.

_Questions_
1. ### How can data from these devices be used by other smart home devices to optimize energy and reduce prices?
Other smart home devices can use our design to optimize energy by utilizing the temperature readings and adjusting other electronics, such as the AC system, within the household for efficiency. They then reduce prices by taking into consideration the time, the temperature outside the home, and the current humidity and alerting the owner of suggested changes within the home since that is not an automated system currently.

2. ### How could the data be used by the general public in a local community network to better predict various weather scenarios?
The data would mainly target farming communities as a resource for agricultural data collection. They would be able to respond to weather changes in proper timing and determine what sort of protections are required for the crops they currently have planted. 

3. ### What sets small consumer weather devices apart from professional-grade machines?
The main differences between small consumer weather devices and professional-grade machines are personalization and scalability. Small consumer weather devices are meant to target specific demographics in their design while allowing users to make changes as their needs change. However, professional-grade machines are meant to handle more data and utilize more sensitive sensors and actuators requiring more power.

4. ### What are the possible privacy and security spencers with using weather monitoring devices that are all connected to the internet?
There are concerns about data privacy as using a device that is connected to the internet would mean that there is a constant stream of personal data, such as personalizations and location tracking being transmitted. There are security risks such as remote hacking for weather devices and data manipulation for devices communicating over WiFi, which can lead to false alerts or a lack of an alert in the user’s preset parameters.

5. ### How can all this data being collected in the home setting be utilized to predict and help with climate change?
The temperature and humidity sensors can provide valuable data on local microclimates, which are smaller, more localized climate patterns. This data (over enough time) could be indicative of broader climate trends like urban heat island effects, changing precipitation patterns, or shifting seasons.


## <u>Design Ideation</u>

The team met in person to brainstorm what the product would look like and what things it would include. We started by looking at the available sensors that we were allowed to use and we settled on two that we wanted to use. From there we moved onto what we wanted to use for the base. After we came up with the different bases, it became clear that every design would include at least one motor. From there we discussed the various ways that we could implement a non-linear actuator to alert the user and what it would be alerting for. Some of this last part of the process was spent looking at various prices and requirements for the second actuator. 

See more about how we went through this in our [Process Breakdown](./appendix.md).

#### Selected Design
We selected the design based on the best combination of the ideas that the team came up with during the Design Ideation process. We went through a process of ruling out specifics that we did not want to include in any design iteration, and from there we developed 3 options. Based on application, creativity, and our requirements, we voted to develop our second design. Our second design was a small, toy boat that included a humidity sensor and a temperature sensor. Throughout the design process, we ended up combining the idea of using multiple motors to control the boat and allowing for forward and both direction motions. This allowed the user to be able to freely control the boat if any obstacles were to arise. The selected design was best suited for the local environment of canals that we chose as Arizona is full of multiple canal systems to help farmers' irrigation systems. See more detail in [Appendix E](./appendix.md).

<div align = "center">
    <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/CAD_Rendering.png">

</div>

## <u>Block Diagram</u>

We started with the basic parameters of the project for the main building blocks. From there we added an actuator from the selected design. Then we went through and added the respective communication lines for each device. Once we determined the microcontroller, we added which pins each component would connect to and the kind of communications they would use. Then we added the voltage, part number, and address for each device. Originally we tried to use motor drivers for our actuators, but we were unsuccessful so we updated the block diagram for that section to be what it currently is. See the fuller image in [Appendix F](./appendix.md).

### Our block diagram meets the following requirements:
6.3 The device will contain at least 2 separate serial sensors that measure a specified aspect of the environment.
6.4 The device will contain at least one serial actuator and one motor or linear actuator with bidirectional control ability.
6.5 The device shall contain at least one voltage regulator of the switching type with a voltage specification of 3.3 V.
6.6 The device will utilize PIC18F47K42T-I/PT & ESP32.


<div align = "center">
    <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Block_Diagram_V7.png">

</div>

## <u>Component Selection</u>
Similarly to how we decided which design we would use, we researched parts that would fulfill the requirements and chose three possibilities. Based on the written pros and cons, we then selected the best option with the exception of non-major components and the microcontroller. After those components were selected and we knew what kinds of signals our sensors and the motor driver would need, one of the team members followed the same process to determine the best microcontroller for our needs. After these were completed, we started adding the necessary materials to our Team Bill of Materials (BOM).

See our full selection process in [Appendix G](./appendix.md).

#### Motor Driver (Actuator Subsystem)

| Solution 1 | Pros | Cons |
| ----- | ----- | ----- |
| <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Comp_Motor_Driver.png"> DRV8830DGQR $1.64 [Link](https://www.digikey.com/en/products/detail/texas-instruments/DRV8830DGQR/2520903)  | 3.6A peak output; Built-in fault protection; PWM control; Legs for easier soldering; Lowest price. | No built-in feedback control will require more coding; May require a heatsink to control overheating. |

This motor driver allows for the most pros out of all drivers and will be most accessible in our scenario. Having the lowest cost will help us drastically with our budget. The peak 3.6A output will be more than enough for the RC boat. The built-in fault protection will help limit any faults that may happen during the design phase of the project. It also allows for PWM control which will be needed for the project requirements and also allows for speed control on our higher RPM motor choice. The 8 legs sticking out of the driver allow for easy soldering and easier mounting while surface mounting, limiting the amount of faults that will occur during construction.

#### Voltage Regulator (Micro-Controller Subsystem)

| Solution 3 | Pros | Cons |
| ----- | ----- | ----- |
| <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Comp_Volt_Reg.png"> LM2596DSADJR4G $2.70 [Link](https://www.digikey.com/en/products/detail/onsemi/LM2596DSADJR4G/2003291) |  Very high maximum output current of 3A; 90% efficiency; Switching at 150kHz; Has a high-voltage range |  Generates a lot of noise; Dropout voltage of 2-4V; Generates the most heat |

Despite the high dropout voltage, this can be remedied using a 12-volt battery to give it more drop-off room. The benefits of using this regulator are that it can support 3A of current which gives us enough room to work with, and has a very high efficiency rating compared to other options given on the list.

#### Humidity Sensor (Sensor 2 Subsystem)

| Solution 3 | Pros | Cons |
| ----- | ----- | ----- |
| <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Comp_Hum_Sen.png"> HIH6030-021-001 14.59$ [Link](https://www.digikey.com/en/products/detail/honeywell-sensing-and-productivity-solutions/HIH6030-021-001/4291625?_gl=1*gdce4m*_up*MQ..&gclid=Cj0KCQjw6oi4BhD1ARIsAL6pox2F7lC9dsWMuQcBle88dzdL_l3uBNudHsvwcUs5quX1dP1AyWQ45oEaAujNEALw_wcB) |  Humidity Range 0 \~ 100% RH; Accuracy ±2% RH; 1.62V \~ 5.5V; Can hand solder it; Big | Most expensive;  Operating range \-40°C \~ 105°C; 8 wires  |

This is realistically the only option we could pick as we have the requirement of hand soldering it and this is the biggest and cheapest option we could go with. All the other options are comparable in accuracy, humidity range, voltage, accuracy, and power draw. So the main contributing factor in making my pick was the ease of mounting to the PCB as we have to do so by hand for our project.

#### Temperature Sensor (Sensor 1 Subsystem)

| Solution 3 | Pros | Cons |
| ----- | ----- | ----- |
| <img src = "https://raw.githubusercontent.com/EmbeddedJellyFish/EmbeddedJellyFish.github.io/main/docs/Comp_Temp_Sen.png"> TC74 $1.15 [Link](https://www.digikey.com/en/products/detail/microchip-technology/TC74A0-3-3VCTTR/443283)   | I2C; Lowest Price; Best Size; Experienced Soldering already | No application for an OpAmp; Accuracy varies by 3 degrees C; Not able to test new temperature sensor |

It is an I2C sensor so that fulfills one of the sensor requirements. One of the product requirements listed creating an alert based on certain readings, and this sensor aligns perfectly with that goal. This sensor also means that I do not need to use an OpAmp as it is already highly accurate and doesn’t require any signal conditioning.

#### Power Budget 
The power budget was used to allow the team to understand if any voltage regulations would need to be in place as well as how long the product could remain operating within one battery charge. After filling in the power budget we concluded that it would be best to use 2 voltage regulators as our maximum current was exceeded and we would need to diversify the power into two separate voltage nets. We also concluded that the product would be able to operate for over 400 hours on a single charge which exceeded our initial user needs. See our Power Budget in [Appendix H](./appendix.md).

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

For more insight into our software development process go to [Appendix I: Software Explored](./Appendix-I.md)

## <u>Presentation 1</u>
[Presentation](./presentation.md)

## <u>System Verification</u>
In the following table, you can see the subsystems that were able to successfully communicate and connect with each other by the end of the semester, and the key for the verification table can be seen in the table that follows.

|  | 3.3V Power Supply | Microcontroller | Temperature Sensor | Motor | Motor Driver | Humidity Sensor |
| 3.3V Power Supply | V KN 12/4 | V KN 12/4 | V KN 12/4 | V KN 12/6 | V KN 12/6 | V KN 12/6 |
| Microcontroller |  | V KN 12/4 | V KN 12/4 | V KN 12/6 | V KN 12/6 | V KN 12/6 |
| Temperature Sensor |  |  | V KN 12/4 | nc | nc | nc |
| Motor |  |  |  | V KN 12/6 | X | nc |
| Motor Driver |  |  |  |  | V KN 12/6 | nc |
| Humidity Sensor |  |  |  |  |  | V KN 12/6 |

| u | unverified connection/subsystem |
| x | connection verified by you |
| (xyz) | serial protocol |
| nc | No Connection |



## <u>Lessons Learned</u>

## <u>Recommendations</u>

