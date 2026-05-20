# AeroSwarm

# GPS-Denied Multi-UAV LiDAR Navigation Simulator

![GPS-Denied Multi-UAV LiDAR Navigation Simulator](https://github.com/1Px-Vision/AeroSwarm/blob/main/Simulator_AeroSwarm.jpg)

[▶ Watch the drone simulator demo on Kapwing](https://www.kapwing.com/e/6a0d77e5d12f18688bafd8ab) 

## Overview

This project implements a **GPS-denied multi-UAV navigation simulator** for testing autonomous drone agents in complex environments. The simulator includes a leader drone and two follower drones flying in a V-formation. The leader uses a simulated **360° LiDAR sensor**, onboard camera view, waypoint navigation, and communication telemetry to guide the swarm through obstacle-rich scenarios.

The system is designed for research and prototyping in:

- GPS-denied drone navigation
- Multi-agent UAV coordination
- LiDAR-based obstacle detection
- Drone-to-drone communication
- Swarm formation control
- Autonomous mapping and telemetry visualization

---

## Main Features

### Multi-UAV Swarm Navigation

The simulator models a small drone swarm composed of:

- **Leader drone**
- **Left follower drone**
- **Right follower drone**

The leader follows the planned path and transfers navigation information to the follower drones. The followers use the received telemetry to maintain formation and follow the leader trajectory.

---

### GPS-Denied Navigation

The simulator is focused on navigation without GPS. The drones rely on onboard sensing, local mapping, and communication between agents.

Supported navigation concepts include:

- Waypoint-based navigation
- Local obstacle avoidance
- Visual navigation dashboard
- LiDAR-based free-space detection
- Formation tracking
- Communication-aware follower control

---

### 360° LiDAR Sensor Simulation

The leader drone is equipped with a rotating LiDAR sensor that scans the environment and detects obstacles around the drone.

The LiDAR module provides:

- 360° ray-based obstacle sensing
- Minimum distance estimation
- Left/right/free-space detection
- Obstacle proximity status
- LiDAR ray visualization
- Safe navigation support

Example LiDAR status shown in the simulator:

```text
LiDAR F/L/R: 1.79 / 0.90 / 0.03 m
LiDAR status: CAUTION
```
---

## Drone-to-Drone Communication

The leader broadcasts its current state to the follower drones. The simulator visualizes communication transfer in real time.

Telemetry includes:

* Leader position
* Leader velocity
* Active waypoint
* LiDAR status
* Packet delivery ratio
* Latency
* RSSI
* Packet age
* Communication health

Example communication log:
```
Leader waypoint + LiDAR transfer

TX L pos=(-0.98,+0.70,+1.00)
speed=0.96 m/s
Waypoint[2]=(-0.24,+1.16,+1.00)
LiDAR F/L/R: 1.79/0.90/0.03 m

-> F_left | RX/LOS | PDR=99.0%
RSSI=-43.7 dBm | LAT=10.9 ms | AGE=0.06 s

-> F_right | RX/LOS | PDR=96.1%
RSSI=-44.5 dBm | LAT=13.6 ms | AGE=0.06 s

```

## Simulator Interface

The graphical interface is organized into several tabs.

### Tab 1: Navigation + Mapping

This tab shows the main simulation dashboard:

* Leader camera
* Left follower camera
* Right follower camera
* Drone HUD displays
* Swarm scenario map
* Leader-to-follower telemetry panel
* Mission timer
* Start, Stop, and Close buttons

### Tab 2: LiDAR + Communication Overlay

This tab is used to inspect LiDAR scanning and communication behavior in more detail:

* LiDAR rays
* Obstacle detection
* Communication links
* Packet transfer status
* Drone formation state

### Tab 3: Sniffer

The sniffer tab is used to monitor communication packets between the leader and the follower drones.

It can be used to debug:

* Packet delivery
* Packet loss
* RSSI level
* Latency
* Communication state
* Follower update timing

### Tab 4: Help Simulator

The help tab provides simulator instructions, control explanation, and mission information.

---

## Sensors Included

The simulator can include the following virtual sensors:

| Sensor               | Description                                               |
| -------------------- | --------------------------------------------------------- |
| LiDAR                | 360° ray-based obstacle detection around the leader drone |
| Camera               | Simulated onboard view for each drone                     |
| IMU                  | Optional inertial information for GPS-denied navigation   |
| VIO                  | Optional visual-inertial odometry estimation              |
| Communication sensor | Simulates packet transfer between drones                  |
| Sniffer              | Monitors drone-to-drone communication packets             |

## Supported Drones

The default simulation uses three drones:

| Drone          | Role                  | Function                                           |
| -------------- | --------------------- | -------------------------------------------------- |
| Leader         | Main navigation agent | Follows waypoints and scans environment with LiDAR |
| Left follower  | Formation agent       | Tracks leader from the left side                   |
| Right follower | Formation agent       | Tracks leader from the right side                  |


## Supported Scenarios

The simulator can be used to test different GPS-denied mission scenarios.

**1. Obstacle-Rich Navigation**

The leader navigates an environment with walls, cylinders, or other artificial obstacles, while the LiDAR detects potential collision zones.

**2. Swarm Formation Flight**

The leader and follower drones maintain a V-formation as they move toward the goal.

**3. Communication Degradation**

The simulator can emulate packet loss, latency, RSSI degradation, and stale telemetry.

**4. LiDAR-Based Avoidance**

The leader detects blocked regions and adjusts navigation based on front, left, and right LiDAR measurements.

**5. Mapping and Mission Monitoring**

The dashboard shows the planned path, drone positions, goal point, obstacles, and current mission status.

### Example Mission Flow
* Start the simulator.
* The leader drone begins following the planned waypoint path.
* The LiDAR sensor scans the environment.
* The leader estimates obstacle distance and navigation state.
* The leader broadcasts position, velocity, waypoint, and LiDAR status.
* The follower drones receive telemetry and maintain V-formation.
* The sniffer monitors packet quality.
* The mission continues until the swarm reaches the goal or the user stops the simulation.

---

## Project Structure

Example project structure:
```
gps-denied-multi-uav-lidar-simulator/
│
├── README.md
├── gps_denied_multi_uav_lidar_simulator.py
├── config.py
├── agents/
│   ├── leader_agent.py
│   ├── follower_agent.py
│   └── llm_policy_agent.py
│
├── sensors/
│   ├── lidar_sensor.py
│   ├── camera_sensor.py
│   └── communication_sensor.py
│
├── scenarios/
│   ├── corridor_scenario.py
│   ├── forest_scenario.py
│   └── obstacle_field.py
│
├── docs/
│   └── simulator_dashboard.png
│
└── outputs/
    ├── telemetry.csv
    └── mission_log.json

```
    
--- 

## Author

Developed for research on GPS-denied autonomous multi-UAV navigation, LiDAR sensing, communication-aware swarm control, and drone-agent simulation.
