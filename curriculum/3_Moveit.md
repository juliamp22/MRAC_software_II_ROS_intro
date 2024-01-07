# Introduction to MoveIt

## Theory

Slides can be found in the software II gdrive folder.

- What is MoveIt!
- URDF / XACRO
- Moveit Setup Assistant
- Kinematic solvers
- Motion planners
- ROS manipulator architecture
- Moveit components
- ROS control
- HW interfaces

## Exercises

### Environment setup

[MRAC_ur_commander](https://github.com/roboticswithjulia/MRAC_ur_commander)

Fork and clone the following repo: MRAC_ur_commander
See repo README for instructions on building, running and using the container.

### Overview of environment

Contents of container:

- ROS noetic
- Moveit

  - IK
    - KDL
    - TRAC-IK

  - Planning pipelines
    - OMPL
    - CHOMP
    - STOMP
    - Pilz Industrial Motion Planner

- UR10e moveit_config (with IAAC calibration) and ur driver. There is a moveit_config with and without end effector.
- [RQT joint trajectory plot](https://github.com/tork-a/rqt_joint_trajectory_plot)
- [industrial reconstruction](https://github.com/gavanderhoorn/industrial_reconstruction) (ros1 branch)
- [realsense-ros](https://github.com/rjwb1/realsense-ros) (with D405 support in ROS1)

Overview of the environment:

- universal_robot/moveit_configs
- move_group_utils
- rqt
- rviz


### Interfacing with Moveit using Python (ur10e_examples)

- ur10e_examples manifest

- moveit commander
- using pilz robot prog
  - sequencer
  - sequence
- sequence from yaml / rosparam
- subframe example

## References

### Moveit

- [moveit noetic tutorials](https://ros-planning.github.io/moveit_tutorials/doc/move_group_python_interface/move_group_python_interface_tutorial.html)
- [moveit move group tutorial python example](https://github.com/ros-planning/moveit_tutorials/blob/master/doc/move_group_python_interface/scripts/move_group_python_interface_tutorial.py)
- [moveit commander source](https://github.com/ros-planning/moveit/tree/master/moveit_commander/src/moveit_commander)
- [moveit_tutorials collision objects](https://github.com/ros-planning/moveit_tutorials/blob/master/doc/collision_environments/scripts/collision_scene_example.py)
- [moveit_msgs wiki](http://wiki.ros.org/moveit_msgs)

### Pilz

- [Pilz Industrial Motion Planner](https://ros-planning.github.io/moveit_tutorials/doc/pilz_industrial_motion_planner/pilz_industrial_motion_planner.html)
- [pilz_robot_programming repo](https://github.com/PilzDE/pilz_industrial_motion/tree/melodic-devel/pilz_robot_programming)

### UR

- [ur IO service](https://github.com/ros-industrial/ur_msgs/blob/melodic-devel/srv/SetIO.srv)



## Assignment 1 - Due date January 14th, 11:59 pm (last git commit)

- Upload a screenshot with the vscode running, terminator and rviz opened after launching the simulation in [MRAC_ur_commander](https://github.com/roboticswithjulia/MRAC_ur_commander?tab=readme-ov-file#launch-the-simulation).


## Assignment 2 - Due date January 19th, 11:59 pm (last git commit)

- Upload a video of rviz with the overall simulation running, making the overall steps of file [commander_examples](https://github.com/roboticswithjulia/MRAC_ur_commander/blob/main/commander/notebooks/commander_examples.ipynb)

## Assignment 3 - Due date January 19th, 11:59 pm (last git commit)

1. Copy the commander_examples.ipynb inside the notebooks and rename it to commander_examples_customized.ipynb inside [commander_examples](https://github.com/roboticswithjulia/MRAC_ur_commander/blob/main/commander/notebooks).
2.  Change the tcp from *rgb_camera_tcp* to *tool_0*, if you execute again the file, what happens? Why the robot behaves differently?
3.  Add another box in the scene, and make a pick and place of this box picking and placing in different places.
