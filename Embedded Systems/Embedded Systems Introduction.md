- 5 Labs + Final project
## Assessment criteria:
- Mini - Labs - 30%
- Final Project (SEEN Prototype + Report) - 30%
- Oral Exam - 40%
### Main Project
#### Smart Environmental & Energy Node (SEEN)

## Module overview:
1. Concept
	2. Application
		3. Validation
			4. Demonstration
## Objectives:
- Introduction to the architecture, design and operation of embedded systems.
- Develop the ability to interface hardware and software in real time environments.
- Hands on experience through the SEEN project.
- Reinforce understanding of real time control communication (MQTT - Message Queueing Telemetry)  and system validation.
- Best practice in safety, reliability and documentation. (This will be reviewed in every lab)
## Learning Outcomes
- Explain key characteristics, architectures and modelling principles of embedded systems.
- Design embedded systems using structured design flow methods
- Implement and debug hardware software interfaces on raspberry pi.
- Integrate sensors actuators and IoT communication into a functional system.
- Validate and evaluate system performance and safety through testing.
## Why study embedded systems
- Embedded systems are the invisible intelligence inside modern technology
- Helps monitor and control a physical process using electronic sensors and actuators
- To drive automation, safety and efficiency across industries
## What are Embedded Systems?
An embedded system is a special purpose computer that performs dedicated functions within a larger electrical or mechanical system
### Key Properties:
- Dedicated function - performs a specific task within a large system
- Real time response - must act within a predictable timing limit
- Resource constrained - designed for efficiency, reliability and low power
- Feedback operation - continuous sensing - decision - actuation cycle
### Applications:
- Aerospace & robotics 
- Energy systems
- Medical tech
- Drone systems
- Home appliances
## Design Process
### Typical Stages of Designing an Embedded System:
- Specification - define functional and timing requirements
- Modelling - represent behavior using diagrams or state machines.
- Design / Implementation - Choose hardware | Develop Software | Integrate Components
- Analysis & Validation - test for timing, safety, and correctness.
- Deployment & Maintenance - embed the controller in the final product
### Design Challenges in Embedded Systems:
- Timing constraints - Tasks must execute within strict deadlines, missing one may cause system failure
- Limited resources- Constrained CPU power, memory, and energy supply 
- Hardware software co-design - functions are split between electronics and code, poor partitioning leads to inefficiency
- Reliability and safety -errors can endanger people or damage equipment

## Real - Time Behavior Concepts in Embedded Systems
- Hard Real Time
	- Missing a deadline = failure (e.g. airbag controller)
- Soft Real Time
	- Late response = Performance degradation (e.g. video streaming)
- Concurrency
	- Multiple tasks must run seemingly at once - scheduling becomes critical.
#### Trade-offs in embedded design
- Performance vs. power consumption
- Cost vs. reliability
##### Reliability, Responsiveness, Fault-Handling

## Architecture of Embedded Systems

- #### Hardware Components
	- Processor
	- Memory
	- Sensors & Actuators
	- Communication interfaces
	- Power supply & Clock

- #### Software Components
	- Application Code
	- Device Drivers
	- Operating System / Scheduler
	- Communication Stack - Handles data transfer (e.g. MQTT; send sensor data to dashboard)
##### Integration Concept:
Performance depends on how efficiently software utilizes hardware resources.

## System Safety & Reliability in Embedded Systems
### Why Safety Matters
- Embedded systems control physical processes
##### Sources of Risk and Failure:
- Hardware faults: Loose connections, sensor drift, voltage instability.
- Software bugs: Unhandled exceptions, timing violations, logic errors.
- Environmental factors: Temperature, vibration, interference.
##### Design for Reliability:
- Redundancy:
- Watchdog timers:
- Error handling and logging:
- Testing and validation: