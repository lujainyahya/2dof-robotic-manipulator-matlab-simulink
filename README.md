# 2-DOF Robotic Manipulator: Modeling, Kinematics, and Control

## Team Members

* Lujain Yahya
* Areen Alakaleek

---

## Project Overview

This project focuses on modeling, analyzing, and controlling a 2-DOF planar robotic manipulator using MATLAB and Simulink.

The robot consists of two revolute joints and two rigid links operating in the X-Y plane. The project demonstrates both kinematic analysis and trajectory control using two different approaches:

1. MATLAB Robotics Toolbox (Kinematics-Based Control)
2. Simulink and Simscape Multibody (Joint-Space Control)

The primary goal is to make the end-effector follow a square trajectory within the robot workspace.

---

## Project Objectives

* Build a robotic manipulator model in MATLAB and Simulink.
* Derive the Denavit-Hartenberg (DH) parameters.
* Implement forward and inverse kinematics.
* Generate and follow a square trajectory.
* Compare Cartesian-space and joint-space control approaches.

---

## Robot Specifications

### Manipulator Configuration

* Degrees of Freedom (DOF): 2
* Joint Type: Revolute-Revolute (R-R)
* Motion Type: Planar Motion (X-Y Plane)

### Link Lengths

| Link   | Length |
| ------ | ------ |
| Link 1 | 0.20 m |
| Link 2 | 0.15 m |

Both joints rotate about the Z-axis.

---

## Denavit-Hartenberg Parameters

| Joint | a (m) | α (rad) | d (m) | θ  |
| ----- | ----- | ------- | ----- | -- |
| 1     | 0.20  | 0       | 0     | θ₁ |
| 2     | 0.15  | 0       | 0     | θ₂ |

### Assumptions

* Planar manipulator
* All twist angles (α) are zero
* All offsets (d) are zero

---

## Solution 1: MATLAB Kinematics-Based Approach

### Description

The robotic arm was modeled using MATLAB Robotics Toolbox and represented using a rigidBodyTree structure.

Inverse kinematics was applied to compute joint angles corresponding to desired Cartesian positions.

### Methodology

1. Create the robot model using DH parameters.
2. Define a square trajectory in Cartesian space.
3. Solve inverse kinematics for each trajectory point.
4. Move the robot along the trajectory.
5. Visualize end-effector motion.

### Square Trajectory Points

| X (m) | Y (m) |
| ----- | ----- |
| 0.15  | 0.05  |
| 0.25  | 0.05  |
| 0.25  | 0.15  |
| 0.15  | 0.15  |

### Results

* Successful trajectory tracking.
* Smooth end-effector motion.
* Accurate inverse kinematics solutions.

---

## Solution 2: Simulink Joint-Space Control

### Description

The robot was implemented using Simscape Multibody in Simulink.

Instead of directly controlling the end-effector position, predefined joint trajectories were applied to the revolute joints.

### Methodology

1. Build the robot using:

   * Solids
   * Revolute Joints
   * Rigid Transforms

2. Generate joint trajectories using:

   * Repeating Sequence (Interpolated)

3. Convert signals using:

   * Simulink-PS Converter

4. Apply motion commands to joints.

### Advantages

* Fully integrated in Simulink.
* Suitable for real-time control.
* Easy extension with controllers, sensors, and actuators.
* Demonstrates practical joint-space control.

---

## Software and Tools

* MATLAB
* MATLAB Robotics Toolbox
* Simulink
* Simscape Multibody

---

## Project Structure

```text
project/
│
├── MATLAB_Code/
│   ├── forward_kinematics.m
│   ├── inverse_kinematics.m
│   └── trajectory_generation.m
│
├── Simulink_Model/
│   └── robotic_arm.slx
│
├── Images/
│
├── Results/
│
└── README.md
```

## Applications

### Industrial Automation

* Pick-and-place robots
* Assembly lines

### Drawing and Plotting Systems

* 2D plotting machines
* CNC-based drawing robots

### Medical and Laboratory Automation

* Precise positioning systems
* Sample handling devices

---

## Results Summary

Both implementations successfully achieved the required square trajectory.

### MATLAB Approach

* Uses inverse kinematics.
* Controls end-effector position directly.
* Provides intuitive Cartesian-space motion planning.

### Simulink Approach

* Uses joint-space control.
* Suitable for simulation of real robotic systems.
* Easily expandable for advanced control strategies.

---

## Conclusion

A 2-DOF planar robotic manipulator was successfully modeled and controlled using MATLAB and Simulink.

The MATLAB solution demonstrated forward and inverse kinematics for Cartesian trajectory tracking, while the Simulink implementation demonstrated joint-space control using Simscape Multibody.

Both approaches successfully tracked a square trajectory and satisfied all project requirements.
