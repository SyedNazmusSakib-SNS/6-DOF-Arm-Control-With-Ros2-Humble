# 6-DOF Robotic Manipulator Control With ROS2 Humble

## Overview
This project involves creating a robotic manipulator using the Robot Operating System (ROS). The manipulator's structure is defined using XML in the Unified Robot Description Format (URDF). The project includes defining materials, links, and joints for the manipulator, and creating launch configurations for the robot state publisher, joint state publisher, and RViz visualization.

## Project Structure
The project directory is organized as follows:

```
robotic_manipulator_project/
├── config/
│   └── config.rviz
├── launch/
│   └── display.launch.py
├── urdf/
│   └── model.urdf
└── README.md
```

## Files

### `urdf/model.urdf`
This file defines the structure of the robotic manipulator, including its materials, links, and joints.

### `launch/display.launch.py`
This file sets up the ROS nodes for the robot state publisher, joint state publisher, and RViz visualization. It configures the launch environment and provides paths to the URDF and RViz configuration files.

### `config/config.rviz`
This file contains the RViz configuration settings used for visualizing the robotic manipulator.

## Setup Instructions

### Prerequisites
- ROS 2 Humble
- `robot_state_publisher` package
- `joint_state_publisher` package
- `joint_state_publisher_gui` package
- `rviz2` package
- `xacro` package

### System Check
1. Verify the operating system:
    ```bash
    cat /etc/os-release
    ```

2. Check ROS 2 installation:
    ```bash
    ros2
    ```

3. Print ROS 2 distribution:
    ```bash
    printenv ROS_DISTRO
    ```

### Installation
1. Update and upgrade the system:
    ```bash
    sudo apt update
    sudo apt upgrade
    ```

2. Install necessary packages:
    ```bash
    sudo apt-get install gedit
    sudo apt install ros-humble-robot-state-publisher
    sudo apt install ros-humble-joint-state-publisher
    sudo apt install ros-humble-joint-state-publisher-gui
    sudo apt install ros-humble-xacro
    ```

3. Verify `rviz2` package prefix:
    ```bash
    ros2 pkg prefix rviz2
    ```

### Creating and Building the Workspace
1. Create the workspace and package:
    ```bash
    mkdir -p ~/ws_manipulator/src
    ros2 pkg create --build-type ament_cmake manipulator
    ```

2. Create necessary directories:
    ```bash
    cd ~/ws_manipulator/src
    mkdir urdf config
    ```

3. Source the setup file:
    ```bash
    source ~/ws_manipulator/install/setup.bash
    ```

### Running the Project
1. Launch the project:
    ```bash
    ros2 launch manipulator display.launch.py
    ```

### Visualization
The RViz visualization tool should open, displaying the robotic manipulator defined in the `model.urdf` file. You can interact with and observe the manipulator's joints and links in the RViz interface.

## Project Details

### URDF File (`urdf/model.urdf`)
The URDF file defines:
- **Materials**: Colors used in the manipulator's visualization.
- **Links**: Different parts of the manipulator.
- **Joints**: Connections between the links, including their types (revolute, prismatic) and limits.

### Launch File (`launch/display.launch.py`)
The launch file:
- Finds the package and URDF model path.
- Reads the URDF model.
- Sets up the `robot_state_publisher`, `joint_state_publisher`, and `rviz2` nodes.
- Configures parameters and arguments for the nodes.

## Contributors
- Syed Nazmus Sakib

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
```

This updated `README.md` file includes all the commands you provided and organizes them in a logical order for setting up and running the project.


