---
title: Software Proposal
---

## Description

The purpose of this page is to visualize the overall software process of each subsystem and how they will interact with each other. The diagram below is an Activity Diagram using UML (Unified Modeling Language) symbolism. The black circle is the start of each subsystem's process. The elongated oval-type shapes represent actions performed by the software. The diamond shapes represent decisions made in the software based on logic. Solid lines between shapes represent the flow inside each subsystem's software. Dashed lines represent information being shared between subsystems.

## UML Activity Diagram

![SoftwareProposalActivityDiagram](image/Team103SoftwareProposal.drawio%20(1).png)


<center>[Download .drawio file](Documents/Private-Use%20Door%20Automation%20Software%20Actvity%20Diagram.drawio)<center>


## Summary

Each software subsystem had two requirements to ensure safety to the user. The subsystems had to wait for calibration and the subsystems had to listen and respond to the motor. The calibration is lead by the rotary sensor where it sends signals to the flex sensor and IR sensors. This signal is sent every 10 degrees. After each signal, all sensors, including the encoder, record analog signal and store it as a variable. This will happen until the rotary encoder reached 90 degrees. When the door opens and closes, at each degree change the sensors will confirm that their current position is similar to the position from the calibration. 

Next, the sensing of object infront or behind the door. The IR sensors will read if there is a user on either side of the door. If there is, the IR sensor will send a signal to the motor. The motor then takes that signal and starts to open the door. If there is something in the way, the IR sensor will see it and send another signal to the motor. If the IR sensor does not read it, the flex sensor will read that it is flexing but that the flex is too much or too little for free motion of the door and send a signal to the door. If either parts of this happen the motor will then stop and wait for further instruction. Depending on the instruction, the door will move back to its previous position or continue to open. This works while it is trying to close as well. 
