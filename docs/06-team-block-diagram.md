---
title: Team Block Diagram
---

## Description

The block diagram below shows how our team's individual subsystems connect to each other. Each major block represents one subsystem showing the programmed microcontroller, which pins of it are being used (and how), and what those pins are connected to. The subsystems will connect to each other via a total of four 8-wire ribbon cables. The pin-headers for these cables are shown at the bottom of each subsystem block, and they display which of their pins are connected to the subsystem. Any pins on the headers that do not have arrows will not be used in the design. The large, bold, bidirectional arrows between subsystems represent the 8-wire ribbon cables themselves, showing which subsytems are directly connected to each other. This diagram helps the team and stakeholders understand the general function of each subsystem as well as how they will be communicating to form a complete system.


## Block Diagram of Subsystems

![Team103 Block Diagram](image/Team103_Block_Diagram.drawio.png)

This is the whole system where each subsystem is connected to another with an 8-wire ribbon cable. The motor is used as a bridge from the flex sensor and the rotary encoder during initial calibration. Every subsystem is then connected to the motor to feed and recieve information from its inputs and motion. 

### Motor

![Motor Block Diagram](https://isrysm52.github.io/01-Block-Diagram/Block-Diagram/)

* Importance:

This subsystem is the main brain of the Automatic Door Opener. The motor takes information from the flex sensor, the rotary encoder, and the two distance sensors to determine if it should move forward or backward. It also uses the information given to stop and wait for more input if there are problems with movement. 








