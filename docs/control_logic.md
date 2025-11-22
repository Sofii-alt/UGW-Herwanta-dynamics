# Control Logic Plan

This document explains how the rover interprets commands, moves safely, and uses sensor feedback to avoid crashing into walls, trees, teammates, or anything else unlucky enough to be in its path.

# Goal

Create a control system that allows the rover to:
- Drive smoothly
- Turn accurately
- Follow mission goals (Stay stable, predictable, and safe)

# Repository Components Related to Control
- software/control/

- `controller_code.py` — main control logic (speed, turning, PID, safety)
- `motor_signal_test.py` — simple script for testing motor outputs
- `README.md` — how to run the control stack
- `hardware/motors/`
- `motor_calculations.xlsx` — torque, RPM, power draw
- `test_results.md` — notes from motor testing and signal checks
- `hardware/battery/`

# Power diagrams
Safety guides (so we don’t accidentally deep-fry the Pi 5)


# How the Control System Works
1. High-Level Commands
The “brain” Raspberry Pi 5 generates commands such as:
- move_forward(speed)
- turn_left(angle)
- stop()
- go_to(x, y)

These commands come from:
- The mapping system (ROS2 navigation stack)
- Manual test scripts during development

2. Convert Commands -> Wheel Speeds
controller_code.py turns those high-level commands into:
- left motors speed
- right motors speed

This is where differential drive math happens:
- forward -> both wheels same speed
- turn -> wheels spin differently
- rotate on the spot -> wheels spin opposite directions

Basically, the Pi tells each wheel:
“Here’s what you need to do. Try not to embarrass us.”

3. Send Commands to Motor Driver
- Since we're not using Pixhawk anymore, the outputs now go directly from the Pi to:
- Motor driver (PWM or motor controller interface)
- Future upgrade: custom PCB for clean wiring
- The Pi sends a signal -> the driver controls the motors.

4. Read Feedback (The Important Part)
The rover uses:
- Wheel encoders -> track actual speed & distance
- IMU -> measure turning, heading, tilt
- LIDAR -> detect obstacles and stop before hitting them

These feedback loops will be used for:
- PID speed control
- Smoother turning
- Better navigation accuracy

5. Avoid Crashing Into Stuff
As the mapping team moves forward, we add:
- Basic obstacle check (LIDAR)
- Emergency stop (yes we still ned one!)
- “Oh no something moved!” logic (dynamic obstacle avoidance)
- Future: full ROS2 navigation safety controller

# Testing Steps
Clear, simple, and in order.

Step 1 Basic Movement
- Run motor_signal_test.py
- Log results in hardware/motors/test_results.md
- Make a simple scripted sequence:
- forward -> stop -> backward

Step 2 Encoder Feedback
- Read encoder values
- Compare expected vs. actual movement
- Tune speed and turning logic
- Test driving a simple square path

Step 3 Safety + Navigation
Future additions:
- Commands published from mission planner
- Safety overrides on LIDAR
- Soft emergency stop
- Hard emergency stop

# TODO (For Control Team)
- Immediate
- Connect motors + confirm basic PWM control
- Implement simple speed control
- Add encoder reading and integrate into controller
- Create small indoor test course

