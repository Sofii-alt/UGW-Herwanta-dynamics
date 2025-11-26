# Software Overview

This folder contains the early software work for my small autonomous rover project.
Everything is still in the “baby steps” phase, so testing ideas, figuring out ROS2, and building the basics for mapping, control, and simple autonomy.

I’ve been experimenting with TurtleBot3 Burger examples to understand ROS2 movement and LIDAR workflows, but since this rover uses different hardware (Raspberry Pi 5, no LIDAR, custom sensors), most things will be adapted or rewritten as I learn more.

This isn’t a finished system. It’s a learning project that grows as I figure things out.

# What This Will Eventually Do
- The goal is to build software that can:
- Read sensor data (IMU, LDR, wheel/motor feedback)
- Build a simple map of the environment
- Keep track of the robot’s position
- Plan paths and follow basic goals
- Run onboard on a Raspberry Pi for off-road use

Right now I’m focusing on the fundamentals:
testing motors, reading sensors, and learning the ROS2 workflow.

# Folder Structure (Quick Tour)
`software/`
- `control/`:  Basic movement tests + motor control scripts
- `mapping/`: First attempts at mapping + simple room visualization
- `mission_planning/`: Early path-planning experiments
- `tests/`: Small scripts for checking sensors, signals, and debugging

Each section has a small README that explains what’s inside. Though for now theres not much in them.

# Next Steps
- Finish installing ROS2 Jazzy + Nav2 on the main Pi
- Try simple SLAM without LIDAR
- Improve mapping and sensor fusion
- Clean up the structure as the project grows
- Add simulation once the real robot becomes more predictable

# Why This Repo Exists
This is a university project, a learning experience, and a place to document progress, not a polished robotics stack (yet).
I’ll keep updating things as I learn more and the rover becomes more capable.

---
# Data flow
<img width="1500" height="2000" alt="image" src="https://github.com/user-attachments/assets/4af0bf23-be87-402e-9e69-5190418e61b9" />

