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


### fork and clone repo

1. create a new workspace:
`mkdir -p ~/dev_ws/src`
`cd ~/dev_ws/src`
2. Fork the repository from [here](git@github.com:roboticswithjulia/MRAC_ur_commander.git) 
3. Download the turtlebot_sim package [MRAC_ur_commander] cloned from your recently forked repository.
`rosdep install --from-paths src --ignore-src -r -y`
4. `cd ~/dev_ws/src`
5. `catkin clean`
6. `catkin build`
7. `source devel/setup.bash`
8. `cd ~/dev_ws/src/turtlebot_sim`
9. `code .` open vscode


### Building the image

1. Open a terminal inside the vscode
2. Running the following command from the root of the repo will execute the build image shell script

```shell
.docker/build_image.sh
```

:warning: Docker build: takes time! Build at the beginning of the class.

&nbsp;

### Running the image

note: On Ubuntu 20.04 *--privileged* flag is required on Ubuntu 22 it can be omitted

Running the following command from the root of the repo will execute the run image shell script

```shell
.docker/run_user.sh --privileged
```

With Nvidia driver

```shell
.docker/run_user_nvidia.sh
```

Once inside the container, ake ownership of the workspace with *write in $USER your user*

```shell
sudo chown -R $USER /dev_ws
```

Open vscode, go to the docker tab.
Select the running container, right click and select attach vscode

&nbsp;

#### Attach vs code to container

In vs code go to the Docker tab in the side bar. Right click on the container named moveit1_ur:latest. Select attach vscode.

When attaching to the container for first time:
In vs code open the command palette (Ctrl-Shift-P). Select `Remote-containers: Open attached container configuration file` | `Open attached container configuration file`. Copy paste content of devcontainer.json and save. Close the vscode window and reattach.


&nbsp;

### Using the container as a development environment

#### Terminal

Terminator is installed in the container for multiple terminals launch terminator from the CLI inside the container. Run `terminator` to start. You will need to source your ros environment.

For automatic sourcing of ros environment add the following to your .bashrc or .zshrc

Add the following to your .bashrc (located in home/$USER) to automatically source the ROS environment when opening a new shell in the container.

```bash
if [ -f "/dev_ws/setup.bash" ]; then
    source /dev_ws/setup.bash
fi
```

or if you are using zsh to your .zshrc

```zsh
if [ -f "/dev_ws/setup.zsh" ]; then
    source /dev_ws/setup.zsh
fi
```

This will source the workspace for every new shell opened in  /dev_ws or /dev_ws/src

&nbsp;

#### Launch the simulation


 Inside the terminal where the docker has been run the .docker/run_user.sh --privileged execute `terminator`

 1. Open a terminal, source to source the ws `/dev_ws/devel/setup.bash` and launch the main manipulator simulation:

    `roslaunch commander ur10e_ka_commander.launch`

 Go to file commander/notebooks/commander_examples.ipynb &rarr; double click and start to run the simulation.

 Make sure that the kernel is Started (Python 3.8.10) and start to execute the different codes.


## Assignment 1 - Due date January 20th, 11:59 pm (last git commit)

- Upload a screenshot with the vscode running, terminator and rviz opened after launching the simulation in [MRAC_ur_commander](https://github.com/roboticswithjulia/MRAC_ur_commander?tab=readme-ov-file#launch-the-simulation).


## Assignment 2 - Due date January 20th, 11:59 pm (last git commit)

- Upload a video of rviz with the overall simulation running, making the overall steps of file [commander_examples](https://github.com/roboticswithjulia/MRAC_ur_commander/blob/main/commander/notebooks/commander_examples.ipynb)

## Assignment 3 - Due date January 20th, 11:59 pm (last git commit)

1. Copy the commander_examples.ipynb inside the notebooks and rename it to commander_examples_customized.ipynb inside [commander_examples](https://github.com/roboticswithjulia/MRAC_ur_commander/blob/main/commander/notebooks).
2.  Change the tcp from *rgb_camera_tcp* to *tool_0*, if you execute again the file, what happens? Why the robot behaves differently?
3.  Add another box in the scene, and make a pick and place of this box picking and placing in different places.
