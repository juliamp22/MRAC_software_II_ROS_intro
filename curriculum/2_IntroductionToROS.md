# Introduction to ROS

&nbsp;

## Theory

Slides can be found in the softwareII gdrive folder.

- What is ROS
- The ROS computational graph
- The ROS filesystem
- ROS tools
- Git and pull requests

&nbsp;

## Environment setup

Fork and clone the following repository: [turtlesim](https://github.com/vinceHuyghe/turtlesim)

Follow the instructions in the README.md file for building, running and using the container.

## Exercises

Follow the tutorials in the links below. Complete the chapters listed under the heading.

- [Understanding ROS nodes](http://wiki.ros.org/ROS/Tutorials/UnderstandingNodes)
  - 5 Roscore
  - 6 Using rosnode
  - 7 Using rosrun
  - 8 Review  
- [Understanding ROS topics](http://wiki.ros.org/ROS/Tutorials/UnderstandingTopics)
  - 1 Setup
  - 2 ROS topics
  - 4 Rostopic continued
  - 5 Using rqt_plot  
- [Understanding ROS Services and Parameters](http://wiki.ros.org/ROS/Tutorials/UnderstandingServicesParams)
  - 1 ROS services
  - 2 Using rosservice
  - 3 Using rosparam

- Creating a catkin workspace and package

  while following this tutorial you do not need to create a new workspace as the docker container already contains a catkin workspace named dev_ws. You can use this workspace to create your package. For reference you can create a new workspace with the following commands:

  ```bash
  mkdir -p ~/dev_ws/src
  cd ~/dev_ws/
  ```

  - [Creating a catkin package](http://wiki.ros.org/catkin/Tutorials/CreatingPackage)
    - 3 creating a catkin package
    - 4 building a catkin workspace

  - [CMakeList.txt](http://wiki.ros.org/catkin/CMakeLists.txt)
    - 1 Overview
    - 2 Overall structure and ordering
    - 3 Cmake version
    - 4 Package name
    - 8 Messages, services and action targets
    - 11.1 Installing Python executable scrips
    - 11.3 installing roslaunch files or other resources

  - [Roslaunch and launch files](http://wiki.ros.org/ROS/Tutorials/UsingRqtconsoleRoslaunch)
    - 2.2 Using roslaunch
    - 2.3 The launch file
    - 2.4 The launch file explained  
      Add the following to your CMakeList.txt file

      ```cmake
      install(DIRECTORY launch/
      DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch)
      ```

      build the workspace with `catkin build` and source the workspace with `source devel/setup`
    - 2.5 roslaunching

    save your changes with git using the following commands

    - `git add .`
    - `git commit -m "your message"`
    - `git push`

  - [Rosbag](http://wiki.ros.org/rosbag/Tutorials/Recording%20and%20playing%20back%20data)
    - 1 Recording data
    - 2 Examining and playing the bag file
    - 3 Recoding a subset of the data
    - 4 Limitations of rosbag

&nbsp;

## Assignment 1

1. Create a GitHub profile if you have not. 
2. Create a repository to play with some text files, and reproduce some working flow, for instance the one studied in the classroom named **IAAC_SoftwareII**. 
3. Document what are you doing in the wiki or Readme.md, telling what are you learning. 
4. Find out other students of the master at GitHub and Follow them. 
5. Let some of your mates to have some development role at your repo. Let them create some branch to develop new things, and finally accept a pull request.
6. Fork some student repository, do some modifications and send a pull request. 
7. Provide the link of your repository.

## Assignment 2

In order to edit code/ files inside the container you will need to attach vscode to the container.

- click on the docker extension in vs code
- select the running container (green play button)
- right click and select attach to container

In the container, create a catkin workspace and package as described above.

- Create a package called `my_package` with a launch file called `my_launch.launch` that launches the following nodes:
- `roscore`
- `rosrun turtlesim turtlesim_node`
- `rosrun turtlesim turtle_teleop_key`

save your changes with git using the following commands

- `git add .`
- `git commit -m "your message"`
- `git push`

## Assignment 3

Add the overall tutorial packages in the repository created in Assignment 1. 

## References

- [ROS tutorials](http://wiki.ros.org/ROS/Tutorials)
- [ROS video tutorials - ROS Noetic for beginners](https://www.youtube.com/playlist?list=PLLSegLrePWgIbIrA4iehUQ-impvIXdd9Q)
