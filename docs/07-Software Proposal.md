---
title: Software Proposal
---

## Description

The purpose of this page is to visualize the overall software process of each subsystem and how they will interact with each other. The diagram below is an Activity Diagram using UML (Unified Modeling Language) symbolism. The black circle is the start of each subsystem's process. The elongated oval-type shapes represent actions performed by the software. The diamond shapes represent decisions made in the software based on logic. Solid lines between shapes represent the flow inside each subsystem's software. Dashed lines represent information being shared between subsystems.

## UML Activity Diagram

![Software Diagram](<image/Team103SoftwareProposal.drawio%20(1).png>)

<center> [Download .drawio file](Documents/Private-Use%20Door%20Automation%20Software%20Actvity%20Diagram.drawio) </center>

## Software Connections

### **Motor**

The motor is the brains of the door. It will take each sensor's information in 1/0 and with a combination of 1/0 will determine if it should move forwards, backwards, or stop.

After the initial calibration, the motor will stay on waiting for a input from one of the IR sensors. Once it gets that input it will start moving based on which IR sensor gave it the input. Once moving, the motor will give each sensor a 1/0 that activates their loops. The motor then constantly waits to see if there is a different input given that would tell it to stop or move in the opposite direction. This constinues until the door is fully closed.

### **IR Distance Sensors**

The distance sensing subsystem is the equivalent of eyes for the system. It is crucial to basic functioning of the system and also the main line of defense in terms of preventative safety measures. It checks it's analog values against the analog values of the rotary encoder subsystem(RES) and sends a binary signal to the motor subsytem(MS) based on the results.

- Upon initial powering of the product, the subsystem waits for a signal from the RES to begin calibration. During calibration, it receives analog values from the RES as the door opens/closes and creates an array of these values matching to the IR detectors' own analog values. The subsystem then goes into "standby mode".

- In "standby mode" the subsystem is checking if the array of values has any discrepancies (there is someone approaching the sensor) and also if the calibration signal is being received. If the calibration signal is received, the subsystem clears the arrays and repeats calibration. If there are array discrepancies, the subsystem goes into "activation mode".

- During "activation mode", the subsystem sends a digital activation signal telling the MS to begin opening the door. The subsystem then continues checking for array value discrepancies (something unexpected is in the path of the door). If discrepancies are found at any point, the subsystem sends a digital alert signal to the MS telling it to stop movement until the discrepancies are resolved, at which point it resumes "activation mode". If no discrepancies are found, the subsystem sends no signals externally as the door opens and closes, then returns to "standby mode".

### **Flex Sensor**

### **Rotary Encoder**

## Summary

Each software subsystem had two requirements to ensure safety to the user. The subsystems had to wait for calibration and the subsystems had to listen and respond to the motor. The calibration is lead by the rotary sensor where it sends signals to the flex sensor and IR sensors. This signal is sent every 10 degrees. After each signal, all sensors, including the encoder, record analog signal and store it as a variable. This will happen until the rotary encoder reached 90 degrees. When the door opens and closes, at each degree change the sensors will confirm that their current position is similar to the position from the calibration.

Next, the sensing of object infront or behind the door. The IR sensors will read if there is a user on either side of the door. If there is, the IR sensor will send a signal to the motor. The motor then takes that signal and starts to open the door. If there is something in the way, the IR sensor will see it and send another signal to the motor. If the IR sensor does not read it, the flex sensor will read that it is flexing but that the flex is too much or too little for free motion of the door and send a signal to the door. If either parts of this happen the motor will then stop and wait for further instruction. Depending on the instruction, the door will move back to its previous position or continue to open. This works while it is trying to close as well.
