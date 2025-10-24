## System Architecture
- Defines the structure of an embedded system. Outlines how components of the system interact and work together to meet the system's requirements.
- Architecture refers to both hardware and software.
- The architecture provides the foundation for ensuring the system meets.
PUT THE FIRST IMAGE FROM THE SLIDES HERE

### Structural Views of Embedded Systems Architectures
Each structure provides a different "Snapshot" of the system.
- Module structures define how software and hardware components are organized.
- Component-and-connector structures describe runtime behavior. (scheduling)
- Allocation structures map software and hardware elements to physical resources / teams.
Together these structures form the complete embedded architecture of a system.

#### Key Characteristics of Embedded Systems Architecture:
- Specialized Functionality
- Efficient Use of Memory
- Efficient Use of Processing Power
- Appropriate Execution Time
- Lower Power Consumption
- Cost Effectiveness
- Reliability & Safety

### Why would System Architecture Matter in Embedded Systems?
- Proper architecture ensures the embedded system meets performance requirements while using minimal resources.
- A good architectural design allows for future upgrades or modifications with minimal effort.
- Clear architectural definitions make systems easier to debug, maintain, and enhance
- Well-defined architecture helps identify potential failure points and ensures that the system remains operational under varying conditions.

## Introduction to Hardware vs Software Partitioning
- Partitioning in embedded systems:
	- Determining which tasks should be handled by hardware and which tasks should be handled by software
		- Goal is to optimize system performance
- Partitioning impacts: Performance, Power Consumption, Cost, Complexity
- Hardware for tasks requiring:
	- Performance critical activities
	- Low-latency tasks
	- Parallel execution
- Software ideal for tasks requiring:
	- Flexibility
	- Frequent Updates
	- Scalability	
### Objectives and Goals of Hardware-Software Partitioning (WIP):
- Performance optimization
- Cost minimization
- Resource Utilization
- Real-Time Responsiveness: Guarantee that real-time tasks meet deadlines, often requiring hardware acceleration or RTOS scheduling
- Low Latency
- Flexibility
- Scalability
INSERT IMAGE HERE TOO

### Quantitative Analysis for Hardware-Software Partitioning
#### System Level Modelling
- Before physical implementation, engineers model system behavior at different abstraction levels to evaluate portioning options
- To analyze functionality timing and communication
#### Quantitative Analysis for Hardware-Software Partitioning
#### UML
- Represents system functionality and task allocation
#### SysML
- Used for architecture and hardware/software interaction
#### MATLAB
- for functional modelling and performance simulation
#### SystemC
- An open source library in C++ that provides a modelling platform for systems with hardware and software components
### Iterative Optimization and Refinement in Hardware-Software Partitioning (WIP):
#### Partitioning as an Iterative Process
- Partitioning is not a linear process, design choices are revisited based on simulation and test outcomes.
FINISH LATER

### Hardware-Software Co-design
- Functional Exploration:
- Architecture Mapping:
- HW-SW Partitioning:
- System Integration:
IMAGE HERE

