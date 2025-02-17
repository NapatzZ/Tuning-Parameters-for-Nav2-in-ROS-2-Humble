# Tuning Parameters for Nav2 in ROS 2 Humble

This document provides a guide on how to tune specific parameters in the Nav2 stack for ROS 2 Humble, based on the changes made in the provided configuration files. The focus is on the parameters that were modified to improve the performance of the navigation stack.

## Overview

The Nav2 stack is a powerful navigation framework for ROS 2, but it often requires parameter tuning to achieve optimal performance for specific robots and environments. This guide highlights the key parameters that were adjusted in the configuration files and explains their impact.

## Tuned Parameters

### 1. **Controller Server (DWB Local Planner)**

The following parameters were adjusted in the `controller_server` section to improve the robot's local planning and control:

- **`max_vel_theta`**: Increased from `1.0` to `2.0` to allow for faster rotational speeds.
- **`min_speed_theta`**: Increased from `0.0` to `0.4` to ensure the robot maintains a minimum rotational speed, reducing the likelihood of getting stuck.
- **`acc_lim_theta`**: Decreased from `3.2` to `3.0` to slightly reduce the angular acceleration limit, providing smoother rotations.

These changes help the robot navigate more efficiently, especially in environments where quick turns are necessary.

### 2. **Local Costmap**

The local costmap parameters were adjusted to improve obstacle avoidance and navigation in dynamic environments:

- **`inflation_radius`**: Decreased from `0.55` to `0.3` to reduce the size of the inflated obstacles, allowing the robot to navigate closer to obstacles without triggering unnecessary avoidance behaviors.

This change helps the robot navigate more precisely in cluttered environments.

### 3. **Global Costmap**

The global costmap parameters were adjusted to improve global path planning and obstacle representation:

- **`robot_radius`**: Decreased from `0.22` to `0.15` to reduce the size of the robot's footprint in the global costmap, allowing for more accurate path planning in narrow spaces.
- **`inflation_radius`**: Decreased from `0.55` to `0.175` to reduce the inflation around obstacles in the global costmap, enabling the robot to plan paths closer to obstacles.

These changes improve the robot's ability to navigate through tight spaces and reduce unnecessary detours.

