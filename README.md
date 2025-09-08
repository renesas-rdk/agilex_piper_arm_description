# agilex_piper_arm_description

ROS2 package containing URDF description files for the Agilex Piper 6-DOF robotic arm.

## Overview

This package provides the robot description for the Agilex Piper robotic arm, including URDF/XACRO files, 3D meshes, and visualization launch files for RViz and Foxglove Studio.

## Usage

### RViz Visualization

Launch with GUI (local):
```bash
ros2 launch agilex_piper_arm_description display_rviz.launch.py run_rviz:=true
```

Launch for remote visualization:
```bash
ros2 launch agilex_piper_arm_description display_rviz.launch.py run_rviz:=false
```

### Foxglove Studio Visualization

```bash
ros2 launch agilex_piper_arm_description display_foxglove.launch.py
```

Connect Foxglove Studio to `ws://<foxglove_bridge_ip>:8765`.

### Using the XACRO Macro

```xml
<xacro:include filename="$(find agilex_piper_arm_description)/urdf/agilex_piper_arm_macro.xacro" />

<xacro:agilex_piper_arm prefix="arm_" parent="base_link">
  <origin xyz="0 0 0" rpy="0 0 0" />
</xacro:agilex_piper_arm>
```

## Robot Specifications

- **DOF:** 6 revolute joints
- **Coordinate frames:** world → base_link → link1-6 → tool0
- **Joint ranges:** -150° to +150° (joint1), 0° to +180° (joint2), -170° to 0° (joint3), ±100° (joint4), ±70° (joint5), ±120° (joint6)

## License

Apache-2.0. URDF model derived from [Agilex Robotics Piper repository](https://github.com/agilexrobotics/piper_ros).
