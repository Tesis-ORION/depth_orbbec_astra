
# depth orbbec astra
[![language](https://img.shields.io/badge/language-c++-239120)](#)
[![OS](https://img.shields.io/badge/OS-Ubuntu_24.04-0078D4)](#)
[![CPU](https://img.shields.io/badge/CPU-x86%2C%20x64%2C%20ARM%2C%20ARM64-FF8C00)](#)
[![GitHub release](https://img.shields.io/badge/release-v3.8-4493f8)](#)
[![GitHub release date](https://img.shields.io/badge/release_date-february_2025-96981c)](#)
[![GitHub last commit](https://img.shields.io/badge/last_commit-february_2025-96981c)](#)

⭐ Star us on GitHub — it motivates us a lot!

## Table of Contents
- [About](#-about)
- [Demostration](#-demostration)
- [How to Build](#-how-to-build)
- [License](#-license)

## 🚀 About

**depth orbbec astra** is a package for ROS2 Jazzy that allow us to use orbbec astra 3D depth camera. This package was originally made by <a href="https://github.com/orbbec/OrbbecSDK_ROS2">Orbbec</a> so all credits to them, we only fixed the package to be compatible with jazzy as it had errors with camera parameters.

## 🎥 Demostration
https://github.com/user-attachments/assets/cd80dca3-5be1-4bcc-9473-98eca3bf71fb

## 📝 How to Build

To build the packages, follow these steps:

```shell
# Add yourself to dialout group if you haven't yet
sudo usermod -a -G dialout $USER

# Go to your workspace/src folder
cd ~/ros2_ws/src

# Clone the repository
git clone https://github.com/orbbec/OrbbecSDK_ROS2.git

# Install required packages
sudo apt install libgflags-dev nlohmann-json3-dev  \
ros-$ROS_DISTRO-image-transport  ros-${ROS_DISTRO}-image-transport-plugins ros-${ROS_DISTRO}-compressed-image-transport \
ros-$ROS_DISTRO-image-publisher ros-$ROS_DISTRO-camera-info-manager \
ros-$ROS_DISTRO-diagnostic-updater ros-$ROS_DISTRO-diagnostic-msgs ros-$ROS_DISTRO-statistics-msgs \
ros-$ROS_DISTRO-backward-ros libdw-dev

# Install udev rules
cd  ~/ros2_ws/src/depth_orbbec_astra/orbbec_camera/scripts
sudo bash install_udev_rules.sh
sudo udevadm control --reload-rules && sudo udevadm trigger

# Return to workspace folder
cd ~/ros2_ws

# Compile the package
colcon build --packages-select depth_maixsense_a010

# Source your workspace
source ~/ros2_ws/install/setup.bash

```
