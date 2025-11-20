#  Control Logic Plan

This file explains how our robot will actually move, understand commands, and not crash into walls.

# Goal
Make the robot respond smoothly to:
- movement commands
- turns
- mission goals
- while keeping everything stable and safe.

# Repo Parts Related to Control
- software/control/
- controller_code.py - main control logic (speed + turning)
- motor_signal_test.py - sends test signals to motors
- README.md - instructions for running control code
- hardware/motors/
- motor_calculations.xlsx - torque + RPM calculations
- test_results.md - notes from motor testing
- hardware/battery/
- power diagrams to help avoid blowing up the Pi by mistake

# How Control Works Simply
1. High-Level Commands
The Pi creates commands like:
- move forward  
- turn left  
- stop  
- go to (x, y)

These will eventually come from:
- mission planner
- mapping system
- manual testing scripts

2. Convert to Wheel Speeds
- controller_code.py converts the commands into:
- left motor speed
- right motor speed
- This is basically the “robot brain” saying: “Okay left wheel, you do this. Right wheel, you do that.”

3. Send Commands to Pixhawk / Motor Driver
- Pixhawk sends PWM or motor signals to the wheel motors.

4. Read Feedback
Use:
- encoder readings
- IMU rotation
- to adjust speed and keep movement stable.

️5. Avoid Hitting Stuff
Eventually we add:
- simple obstacle check
- emergency stop
- “Oh no! Something moved!” logic

# Testing Steps
Step 1
- Run motor_signal_test.py
- Document results in test_results.md
- Make simple script: forward -> stop -> backward
Step 2
- Integrate encoder feedback
- Test turning accuracy
- Try to drive a square shape

Future:
- publish commands from mission planner
- add safety layer

# TODO (For Team)
- Connect motors + test signals
- Implement basic speed control
- Add encoder reading support
- Make small test course
- Document in tests/signal_check.py
