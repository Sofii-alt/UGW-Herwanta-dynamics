# Control Logic Plan

This document outlines the architecture and methodology for the rover’s control system. It describes how high-level navigation commands are translated into low-level motor actions, how sensor feedback is integrated, and how safety mechanisms are implemented.

# Objectives
- Provide reliable and stable motion control for the rover
- Translate navigation goals into differential drive motor commands
- Integrate encoder and IMU feedback for closed-loop control
- Establish a foundation for autonomous navigation within ROS2

# Relevant Repository Components
- `software/control/`
- `controller_code.py` core control logic, speed regulation, turning behaviour
- `motor_signal_test.py` motor output and signal verification
- `README.md` execution instructions and development notes
- `hardware/motors/`
- `motor_calculations.xlsx` torque, RPM, and power analysis
- `test_results.md` collected motor and signal test data
- `hardware/battery/`

# Power distribution diagrams
Safety notes for protecting Raspberry Pi and motor driver hardware

# Control Architecture Overview
1. High-Level Commands
Commands originate from:
- Manual test scripts
- ROS2-based mapping or navigation modules
- Future mission planning software

Commands typically include:
- Linear and angular velocity targets
- Rotation commands
- Position-based goals (future integration)

2. Motion Conversion
controller_code.py converts high-level commands into low-level wheel velocities.
This includes:
- Differential drive kinematics
- Speed limiting and smoothing
- Basic trajectory shaping

3. Motor Interface Layer
Raspberry Pi communicates directly with the motor driver.
This layer handles:
- PWM generation
- Direction control
- Low-level actuation reliability
- Pixhawk has been removed from the design and replaced with a dual-Raspberry Pi architecture.

4. Feedback Integration
The control loop incorporates:
- Wheel encoders for odometry and velocity estimation
- IMU data for orientation and turn accuracy
- Optional LIDAR checks for safety and collision avoidance
- This enables closed-loop corrections for more predictable motion.

5. Safety & Obstacle Handling
The system will later include:
- Real-time obstacle checks from LDR
- Software-based emergency stop
- Safety thresholds for motor current and battery protection


# some quick drawings
<img width="1500" height="2000" alt="image" src="https://github.com/user-attachments/assets/4af0bf23-be87-402e-9e69-5190418e61b9" /> 
