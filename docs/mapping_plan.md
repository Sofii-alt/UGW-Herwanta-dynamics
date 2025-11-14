# Overview

This document outlines the plan for implementing the mapping system for our autonomous ground robot.
Our main goal: create a reliable SLAM pipeline that can run on a Raspberry Pi 4 + Pixhawk 6C setup without melting either component.

# Objectives
- Build a 2D map of the environment
- Fuse data from sensors (IMU, wheel encoders, lidar (, a camera in the future))
- Enable localization (robot knowing where it is on the map)
- Provide the navigation system with a usable map + pose estimate
- Keep CPU usage low enough so the Pi doesn’t spontaneously enter orbit

# Components
- ROS2 (Humble)
- slam_toolbox (for Pi)
- MAVLink connection for state + IMU
- Wheel encoders (when hardware team gives them)

# Mapping Pipeline Plan
Data Input
- /mavros/imu/data from Pixhawk
- /encoders (custom topic)
- /scan if lidar exists
- /camera if visual SLAM

Preprocessing
IMU → filter
Encoders → odom node
Sensor fusion into /odom
Publish transforms (/tf)
SLAM Node
Launch slam_toolbox
Real-time map building mode
Adjust parameters (scan resolution, frequency, loop closure)

# Map Output
- /map (2D occupancy grid)
- /map_metadata
- /pose estimate
- Save map to file for future navigation

---
# Testing Strategy
- Test inside SITL + Gazebo first
- Slowly add sensors
- Tune until the map stops looking like modern art
- Field tests in a hallway (slow robot = fewer lawsuits)

 # To-Do
 - ROS2 workspace
 - MAVROS connection test
 - SLAM toolbox installation
 - Odom calculations (when encoders mount)
 - First real map
 - Parameter tuning


