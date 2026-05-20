# AeroSwarm

# GPS-Denied Multi-UAV LiDAR Navigation Simulator

![GPS-Denied Multi-UAV LiDAR Navigation Simulator](https://github.com/1Px-Vision/AeroSwarm/blob/main/Simulator_AeroSwarm.jpg)

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

___ 
## Sensors Included

The simulator can include the following virtual sensors:
