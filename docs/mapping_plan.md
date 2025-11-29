# Mapping Plan
This file explains how we handle mapping for our robot.
The goal: make the robot understand where it is without panicking, getting lost, or mapping our feet as “permanent obstacles.”

---

# What We’re Trying to Achieve
- Build a 2D map of indoor and outdoor test spaces  
- Track the robot’s position on that map using odometry  
- Use the map for navigation and missions  
- Keep everything lightweight enough for Raspberry Pi 5 (8GB)  
- Make the system modular so we can improve it as our skills improve


# Repo Structure (Mapping-Relevant Files)
**software/mapping/**
- `map_processing.py`: takes sensor inputs -> produces odometry + map updates  
- `room_visualization.py`: visual output of map, debugging tools  
- `slam_config/`: future folder for SLAM parameters (ROS2 yaml)

**sensors/**
- `lidar_test_logs.md`: results from vacuum-LiDAR tests  
- `wiring_diagram.png`: how LIDAR + encoders + IMU connect  
- (future) `encoder_notes.md`  
- (future) `imu_calibration.md`

**tests/**
- mapping experiments  
- hallway recordings  

---

# Mapping Pipeline 
We follow a standard ROS2-style SLAM process:

# Collect Sensor Data
Data sources:
- LIDAR (USB, 360° scans)  
- Wheel encoder ticks: distance  
- IMU (if available): rotation  
- Timestamps for synchronization  
-> All of this runs directly on the **main Raspberry Pi 5**.

---

# Produce Odometry (robot position estimate)
Inside `map_processing.py` we combine:
- encoder displacement  
- IMU angular velocity  
- time differences  
Outputs a clean `/odom` topic (ROS2).

---

# Build the 2D Map
We use a lightweight SLAM implementation on the Pi:
- LIDAR scans -> detect walls and obstacles  
- Odometry -> estimates robot movement  
- SLAM -> updates occupancy grid map  
Final result: a live map the robot can use later to navigate.

---

# Visualize + Save Map
Using `room_visualization.py`:
- real-time map view  
- save map snapshots (PNG)  
- store data for later missions  
Later we’ll integrate RViz2 once everything is stable.

---

# Testing Plan

# Sensors Only
- Test LIDAR -> write logs into `sensors/lidar_test_logs.md`  
- Visualize scan data  
- Build a tiny prototype map (even if it looks like potato-quality)  
# Add Motion
- Add encoder + IMU fusion  
- Small hallway walking test  
- Try not to map your legs or teammates  

# Robot Rolling
- Real SLAM test on wheels  
- Tune odometry until drift stops being “drunk mode"  
- Save first full map to `/tests/`  


