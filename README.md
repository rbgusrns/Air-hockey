# Air Hockey Robot

Autonomous air hockey robot project developed in 2023. This repository combines the vision pipeline, embedded motor-control firmware, and mechanical design assets used to build a single-player air hockey system.

## Overview

- Tracks the puck with OpenCV-based image processing.
- Predicts the puck trajectory and expected arrival time in real time.
- Sends trajectory data from the vision PC to the controller over serial communication.
- Drives a two-axis striking mechanism to intercept and return the puck.

This project was built around the idea of creating a simple sports robot that a single user can enjoy alone while also serving as a hands-on robotics platform for embedded control, computer vision, and mechanical design.

## System Flow

1. A camera captures the air hockey table in real time.
2. `AirHockey_trace.py` detects the puck and extracts motion information with OpenCV.
3. The PC predicts the puck path, bounce points, and arrival timing.
4. Position and timing data are transmitted to the MCU through SCI serial communication.
5. The controller computes motor movement and drives the striker to the target point.

## Key Components

### Hardware

| Item | Model / Note |
| --- | --- |
| MCU | TMS320F2808PZA |
| Camera | SM-A908N |
| Motor | ROB-09238 |
| Motor Driver | I298N |
| PC Processor | Intel Core i5-1035G1 |

### Software

| Item | Detail |
| --- | --- |
| Languages | C, Python |
| IDE | Source Insight, VSCode |
| Main Library | OpenCV |
| Communication | SCI serial communication |

## Repository Structure

| Path | Description |
| --- | --- |
| `AirHockey_trace.py` | OpenCV-based puck detection, path prediction, and serial transmission logic |
| `main/` | Firmware source for the TI C2000-based controller and motor-driving logic |
| `include/` | Header files and shared embedded definitions |
| `Compiler/` | Embedded toolchain resources used by the firmware build setup |
| `3D Parts/` | Mechanical CAD parts for the air hockey robot assembly |
| `exhibition.zip` | Archived project artifact distributed with the repository |

## Architecture

![Architecture diagram](https://github.com/user-attachments/assets/738102cb-2acf-49be-8a5d-71bd51095ae2)

## Highlights

- Combines computer vision and embedded motion control in one robotics project.
- Uses predicted puck travel instead of only reacting to the current puck position.
- Includes firmware, vision code, and 3D part files in a single repository.
- Serves as a compact reference project for robotics competitions and capstone-style demonstrations.

## Demo

- Overview video: https://youtu.be/xwHemnOOevc?feature=shared

## References

This README structure was refreshed with inspiration from competition-oriented robotics documentation patterns seen in:

- JP Robotrace projects and related competition pages
- MUC-style contest repositories with structured overview and schedule-oriented documentation
- AD Challenge documentation with clear objective and resource-link sections
