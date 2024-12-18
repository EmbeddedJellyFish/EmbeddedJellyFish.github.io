# Software Explored

[Code Repository](https://github.com/EmbeddedJellyFish/Code)

### Process
&nbsp;&nbsp;&nbsp;We started with the most basic version of what our design would do, which consisted of the microcontroller reading and displaying the data from the sensors. From there we developed the actuator subsystem and designed it so that there would be a cycle of the motors turning on and off based on where the user desired the boat to go. Then we added aspects that would satisfy user interface needs such as allowing the user to choose what route the boat should follow and displaying the data in a user-friendly manner. A lot of this was done on a one-on-one basis where the original creator of the UML would discuss the desires of the owner of that subsystem and then translate that into a program diagram. 

### Changes
The following are the top 5 biggest changes to our software design since the original proposal. 

1. #### Updated flow and interrupts to include a time delay to prevent data overwrite. 
   Originally, the system was designed to collect and process data from various sensors at a constant rate without any time delay. This could result in data overwriting where new data would overwrite old data before it was fully processed. To fix this, we added a time delay in the flow of data collection, which ensures that each data point has adequate time for processing and transmission before the next one is collected. This change ensures that data overwriting is prevented, and the system handles sensor data in a controlled and orderly manner.

2. #### Updated aesthetics for readability purposes. 
   Initially, the UML diagram had elements that were visually cluttered, making it difficult to quickly understand the flow of data or the interactions between different subsystems. The layout did not optimize space, and key components were difficult to distinguish during presentations. So we updated the aesthetics by reorganizing elements, reducing visual clutter, and creating more space between subsystems for better clarity. I also ensured that line styles were used effectively to differentiate between various types of interactions and increased font size.

3. #### Removed unnecessary nested loops and interlocking loops.
   The original design included nested loops and interlocking loops in the system's process flow, which made the logic unnecessarily complex. These loops were creating inefficiencies in the system, potentially leading to unwanted delays or unpredictable behavior due to the system getting stuck in complex cycles. So we refactored the diagram by eliminating redundant loops and simplifying the flow of operations. Instead of using nested or interlocking loops, we streamlined the logic by creating clearer decision paths and using sequential steps where possible. This change made it so the system can now process tasks in a more linear, predictable manner without getting slowed down by unnecessary cycles.

4. #### Added outputs and inputs for the various subsystems.
   Initially, some of the subsystems were not clearly defined with explicit inputs and outputs. This made it unclear how data was being passed between subsystems and where information was coming from or going. It was difficult to track the flow of data and understand the interdependencies between different system components. To fix this, we added explicit inputs and outputs to each subsystem in the diagram to clarify how data flows between them. These changes help visualize the system's data flow and improve the understanding of how each component interacts with others.

5. #### Changed motion delays to account for the time it takes for the boat to move between positions and complete a cycle. 
   The original motion delays in the system did not take into account the actual time required for the boat to physically move between positions and complete its cycle. This could lead to inaccurate timing or premature actions, as the system might attempt to act before the boat has completed its current task or reached the correct position. To resolve this, we modified the motion delays to account for the actual time it takes for the boat to move between its positions. This involved adjusting the timing parameters and ensuring that delays were introduced in the process flow so that the boat had adequate time to complete its movement and return to a stationary state before the next cycle began. This change improves the synchronization between the boat’s movements and the system’s actions, preventing errors and ensuring the system works smoothly and predictably during each cycle.

### Version 2.0
&nbsp;&nbsp;&nbsp;&nbsp;In creating a Version 2.0 of the software design, we would focus on several key areas of improvement: enhancing system reliability, simplifying code for better maintainability and debuggability, and optimizing data flow and communication protocols. The updated design would aim to create a more robust, efficient, and scalable system that can handle future growth and integration with additional features or sensors.
&nbsp;&nbsp;&nbsp;&nbsp;To improve reliability and stability, we would incorporate redundancy mechanisms for critical subsystems, such as sensor data acquisition and data transmission. For example, adding error-checking routines and data validation would prevent the system from acting on corrupted or inaccurate sensor readings. Implementing watchdog timers would also help prevent the system from freezing or entering into infinite loops due to unforeseen conditions. Additionally, we could consider implementing a fall-back protocol in case of failures in communication such as WiFi failure resulting in the use of a temporary local storage and periodic attempts to reconnect. This change would make the system more resilient in real-world operating conditions.
&nbsp;&nbsp;&nbsp;&nbsp;One of the most significant improvements we would focus on is making the code more modular and easier to debug. In Version 1.0, the system has large monolithic functions and tightly coupled code, which can make it difficult to isolate issues during testing. In Version 2.0, we would refactor the software into more modular, function-based components. This refactoring would also make the system easier to update in the future by allowing us to add new sensors or peripherals with minimal disruption to other parts of the code. For example, if a new motion sensor was added, it could be implemented as a new module without changing the core logic of the system. 
&nbsp;&nbsp;&nbsp;&nbsp;To optimize the communication protocols, we would focus on improving the efficiency of data transmission and making it more robust. In Version 1.0, the system uses MQTT over Wi-Fi to transmit data. While this is an efficient protocol, we would consider incorporating data compression techniques to reduce bandwidth usage, especially if the system is expected to handle large amounts of sensor data.
&nbsp;&nbsp;&nbsp;&nbsp;Additionally, we would implement error-checking mechanisms like checksum validation for each data packet sent via MQTT to ensure data integrity. If a packet is corrupted during transmission, the system would be able to request a retransmission without losing critical information.
I would update the flow diagram to include: Modular components that clearly show the separation of tasks (e.g., sensor reading, data processing, actuation).
Redundancy and error handling, including decision points for retrying failed operations (e.g., lost communication or sensor errors).
New peripherals, like real-time clocks and encoders, are integrated into the system with clear communication protocols (I2C/SPI).
More robust communication, including data validation, error checking, and QoS adjustments in the MQTT transmission.

### MCC Configurations

![JPG Image](docs/mcc_1.png)
![JPG Image](docs/mcc_2.png)
![JPG Image](docs/mcc_3.png)
![JPG Image](docs/mcc_4.png)
![JPG Image](docs/mcc_5.png)
![JPG Image](docs/mcc_6.png)

### UML Diagram

![JPG Image](docs/UML-1.png)

[Appendix](./appendix.md)<br><br>
[Back to main page](./index.md)