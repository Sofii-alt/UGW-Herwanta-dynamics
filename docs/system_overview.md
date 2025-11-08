# Robot Project System Overview

This project aims to build a mobile robot capable of mapping its environment and performing basic autonomous navigation.

## Components

- **LIDAR sensor:** Measures distances to obstacles and maps the environment.
- **Motors & Encoders:** Move the robot and provide wheel odometry.
- **Battery pack:** Powers the robot.
- **Controller board:** Runs ArduPilot/ROS and communicates with sensors.
- **Mission planning software:** Receives map data and sends navigation commands.

## Data flow
LIDAR → Controller → Mapping software → Mission planning → Motors
Battery → Powers all components


## Goals
- Step 1: Remote control and simple sensor visualization
- Step 2: Room mapping and localization
- Step 3: Autonomous navigation with planned waypoints


