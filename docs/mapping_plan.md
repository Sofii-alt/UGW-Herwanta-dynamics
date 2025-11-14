# Mapping Plan
This file explains how we will handle mapping for our robot.
The goal is simple: make the robot understand where it is and what the room looks like without panicking or drawing abstract art.

# What We’re Trying to Achieve
- Build a 2D map of rooms or hallways
- Track the robot’s position on that map
- Use the map later for path planning and missions
- Keep everything light enough to run on a Raspberry Pi 4

# What files do what
These are the files/folders in our repo connected to mapping:
- software/mapping/
- README.md — instructions for running mapping code
- map_processing.py — processes sensor data
- room_visualization.py — shows the map visually
- sensors/
- lidar_test_logs.md — notes + test results from the vacuum LIDAR
- wiring_diagram.png — how sensors connect
- (for future: encoder data, IMU notes)

# Simple mapping pipeline
1. Gather Sensor Data
Data we’ll use:
- LIDAR from the vacuum
- Wheel encoder data (when the harware team gives them)
- IMU from the Pixhawk
- These will later be combined.

️2. Convert This Into Odom Data
We produce a clean “robot position estimate” using:
- encoder distance
- rotation from IMU
- time stamps
- This goes into map_processing.py.

3. Build a 2D Map
We run a mapping algorithm (SLAM) on Raspberry Pi:
- takes LIDAR scans
- takes odom
- updates the map

4. Visualize + Save the Map
Using room_visualization.py to:
- draw the map
- save it for mission planning later

# Testing plan
Step 1
- Test LIDAR from vacuum -> write logs to lidar_test_logs.md
- Run simple map building in Python (even a basic occupancy grid)
Step 2
- Add IMU + encoder fusion
- Small hallway test
- Try not to map your shoes as obstacles

# TODO (For Team)
- Clean up LIDAR data logs
- Add encoder -> odom code
- Build first map prototype
- Write short results in tests/ folder
