# whats needed
This part is ment for desingning the software for a rover, capable of mapping, localization, and basic autonomous navigation.
---


# Role A — Control Systems & Hardware Integration
Focus: Making the robot physically move and ensuring all hardware sensors communicate properly.

Responsibilities:

1. Pixhawk & ArduPilot
- Flash ArduPilot Rover firmware
- Configure motor outputs, PID, vehicle params
- Set up safety settings (failsafe, battery monitor)
- Test the vehicle in SITL + real hardware

2. Sensor Integration
- Connect + test LIDAR, IMU, wheel encoders
- Write simple test scripts (Arduino or Python)
- Ensure sensors publish clean data (correct units, rates, calibration)

3. Communication Layer (ROS2 ↔ Pixhawk)
- Install MAVROS2
- Set up serial/UART between Raspberry Pi ↔ Pixhawk
- Expose required topics:
/odom
/scan (if LIDAR via Pixhawk)
/imu/data_raw
/cmd_vel

4. Hardware Documentation
- Wiring diagrams
- Voltage requirements + power budget
- Notes on regulators, fuses, and safe power design

Role B — Mapping, Localization & Autonomy
Focus: Making the robot understand its environment, localize itself, and navigate intelligently.

Responsibilities:

1. Mapping (SLAM)
- Setup and configure slam_toolbox
- Process LIDAR data
- Generate occupancy grid maps
- Tune scan matching, filtering, and mapping parameters
- Save/export map results for testing

2. Localization
- Implement AMCL (or SLAM mode)
- Fuse odometry + LIDAR + IMU
- Verify robot position accuracy in RViz2

3. Navigation & Mission Planning (Nav2)
- Configure planners (DWB, TEb, RPP)
- Create costmaps
- Write simple waypoint scripts
- Implement mission plans:
-- “Go to X, Y”
-- “Visit waypoints in order”
-- “Map unknown region”

4. Simulation
- Run ArduPilot Rover SITL
- Test navigation before hardware is complete
- Document results with screenshots and example runs

---
# Shared Responsibilities

Documentation
- Keep /docs/ updated
- Record test results
- Maintain clean Git commits with clear messages

Testing
- Weekly tests (simulation or real hardware)
- Debugging unexpected behavior
- Cross-check each other’s output topics and logs

DevOps & GitHub
- Keep repository organized
- Use branches for new features
- Review each other’s pull requests



# Milestones

1. Mapping Demo
- LIDAR working
- Basic SLAM map in RViz2
2. Localization
- Stable /odom
- Robot knows where it is in the map
3. Navigation
- Robot follows a single goal point
4. Missions
- Robot completes a multi-waypoint mission
- Mapping + autonomy fully integrated

  
