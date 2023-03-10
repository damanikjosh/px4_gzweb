# Docker Environment for PX4 Development with ROS2 Foxy and Gazebo Web Simulation (gzweb)

This repository contains a Dockerfile to build a Docker image for PX4 development with ROS2 Foxy and Gazebo Web Simulation (gzweb). This docker image can be used to run the PX4 SITL simulation on headless infrastructure. The Gazebo client is served via a web browser.

## Prerequisites

- Git
- Docker

## Build the Docker Image

Clone this repository and build the Docker image:

```bash
git clone https://github.com/joshuadamanik/px4_gzweb.git --recursive
cd px4_gzweb
docker build -t px4_gzweb:latest Dockerfile-<arch>
```

where `<arch>` is the architecture of your host machine. The following architectures are supported:
- `amd64` (x86_64)  : Linux, Windows
- `arm64` (ARMv8) : macOS

## Run the Docker Container

Attach two terminals to the Docker container.

Terminal 1:
```bash
HEADLESS=1 make px4_sitl gazebo-classic
```