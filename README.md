# Rover Project: Autonomous Mapping and Paintball System

Welcome to our student rover project! This is a small-group work-in-progress autonomous ground robot that can map its surroundings, navigate, and has a paintball/marking system on top.

The aim is to combine mechanical design, control systems, mapping, and system integration, while learning real-world robotics skills.
Note: Everyone contributes a bit across the teams since this is a small student project.

# Robot showcase
<img width="993" height="555" alt="image" src="https://github.com/user-attachments/assets/5438a811-fe35-4a20-8259-51b2504890c0" />
A preliminary sketch for the robot without the paintball gun yet.

---
# Project Goals
- Develop a rover that can map rooms or outdoor areas using LIDAR, wheel encoders, and IMU.
- Implement basic navigation and motor control using Raspberry Pi 5.
- Integrate a paintball/marker system for testing actuation and targeting.
- Learn and practice mechanical, electrical, and software integration.
- Long-term: build a terrain-ready rover that autonomously maps areas and marks trees for forestry operations.

# Repository Structure
`design_sketches/`   -> mechanical drafts, CAD files, 3D renderings  
`hardware/`          -> motors, batteries, sensors, wiring diagrams, calculations  
`software/`          -> control scripts, ROS2 nodes, mapping, navigation  
`tests/`             -> logs, LIDAR data, sensor diagnostics, experiments  


Team Structure
---
#Team 1: Mechanical
Members:
Aatu -> calculations, design
Veeti -> 3D renderings, design
Eelis -> stability calculations
Responsibilities: 
- Chassis construction
- Motor selection and installation
- Encoders, battery mounting, electronics layout
- Mechanical stability and durability

Team 2: Paintball / Marking System
Members:
Leo -> design and actuation of the paintball system
Responsibilities:
- Mechanical and electrical integration of the marking system
- Testing firing mechanism
- Working with mechanical and software teams for safe operation

Team 3: Mapping, Controls & System Integration
Members:
Sofia -> mapping, navigation, control, ROS2, system integration
Responsibilities:
_ SLAM setup and testing
- Navigation stack
- Motor control and sensor fusion
- System-wide testing and integration

---

# Current Progress
- Mechanical: chassis designed, early 3D renders complete, bought wheels and 4 motors. Starting to build basic structure
- Electrical: motor & battery calculations ready
- Sensors: repurposed a Roborock vacuum LDR. Thinking of ordering a 3D LiDAR
- Hardware: Two Raspberry Pi 5 (8GB) have been set upp as main computers -> One Pi for system control & mapping (ROS2), one Pi for the paintball/marking system
- Software: learning (ROS2 Jazzy, SLAM, NAV2, Gazebo)
-> Decision: Pixhawk and ArduPilot removed from the system to simplify early development
