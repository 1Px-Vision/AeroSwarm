# AeroSwarm

# GPS-Denied Multi-UAV LiDAR Navigation Simulator

![GPS-Denied Multi-UAV LiDAR Navigation Simulator](docs/simulator_dashboard.png)

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
