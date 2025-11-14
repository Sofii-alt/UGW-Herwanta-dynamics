# Forest rover Project

# Autonomous Mapping & Mission Planning Robot

[Consept picture]
*Figure 1: Concept sketch of the robot (LIDAR on top, motors and encoders below, controller in middle......)*

---

## Overview
This project is a student-designed mobile robot aimed at exploring autonomous mapping, localization, and mission planning. It integrates mechanical, electrical, and software systems to demonstrate real-world robotics principles.

The robot uses:
- **LIDAR** for 2D mapping and environment sensing
- **Motors & encoders** for movement and odometry
- **Battery pack** for power management
- **Controller board** running ROS2/ArduPilot for software integration
- **Mission planning software** for autonomous navigation

---

## Project Goals
1. **Remote Control & Motor Testing** – Verify that motors, encoders, and sensors function correctly.  
2. **Room Mapping & Visualization** – Use LIDAR and wheel odometry to create 2D maps.  
3. **Autonomous Navigation** – Navigate to predefined waypoints using mapping data.  
4. **Future Work:** Full SLAM-based navigation with obstacle avoidance.

---

## Team Members
| Member | Role |
|--------|------|
| Leo    | Aiming & Sensors (additional sensors, aiming system software)                             |
| Veeti  | Mechanical Design (chassis, wheels, mounts) ; Electrical Design (motors, battery, wiring) ; 3D modeling and illusitration |
| Aatu   | Mechanical Design (chassis, wheels, mounts) ; Electrical Design (motors, battery, wiring) |
| Sofia  | Mapping & Control (LIDAR, SLAM, software integration)                                     |
| Eelis  |                                                                                           |

---

## Repo Structure
/docs - Documentation, plans, sketches, and budget
/hardware - Motor, battery, and sensor details; vacuum teardown
/software - Code for mapping, control, mission planning, and tests
README.md - Project overview and progress summary

---

## Current Progress
- Rower desines are almost finished.
- Budget sheet created with initial cost estimates and priority tracking.  
- GitHub structure fully organized.  
- Roborock vacuum partially dismantled for reuse of LIDAR, motors, encoders, and battery.  
- Linux live USB prepared for software development and simulation.  
- Placeholder scripts created for mapping, control, and mission planning.  
- Sample LIDAR datasets visualized in Python and RViz.  


[Sample LIDAR Map] 
*Figure 2: Example of 2D point cloud visualization using sample LIDAR data......*

---

## Next Steps
- Complete Roborock teardown and document all reusable components.  
- Connect LIDAR to the controller and verify real-time data acquisition.  
- Test motor drivers with Roborock wheels and encoders.  
- Implement basic SLAM and mapping using Python or ROS2.  
- Begin mission planning integration for waypoint navigation.  
- Update GitHub with test logs, diagrams, and screenshots of functioning modules.

---

**Highlights:**
- `/docs` contains system diagrams, mapping plan, control logic, and budget planning.  
- `/hardware` contains motor and battery calculations, sensor test logs, and vacuum teardown documentation.  
- `/software` contains mapping simulation scripts, motor control placeholders, mission planning pseudocode, and integration tests.  

---

## Important Files & Links
- **Documentation:** `/docs` (system overview, mapping plan, control logic, sketches)  
- **Hardware calculations:** `/hardware/motors/motor_calculations.xlsx` & `/hardware/battery/battery_calculations.xlsx`  
- **Mapping software:** `/software/mapping/map_processing.py`  
- **Control software:** `/software/control/controller_code.py`  
- **Mission planning:** `/software/mission_planning/path_planning.py`  
- **Tests & simulations:** `/software/tests/`  

---

## Skills Demonstrated
- System-level thinking: Integration of hardware & software modules.  
- Practical robotics: Working with sensors, motors, and mapping algorithms.  
- Project management: Modular GitHub structure, documentation, and planned testing workflow.  
- Innovation & initiative: Reuse of commercial hardware for research-grade robotics development.  

---

## Screenshots / Diagrams Placeholder
- Add `/docs/design_sketches/robot_concept.png` → concept diagram  
