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

While following this tutorial you do not need to create a new workspace as the docker container already contains a catkin workspace named dev_ws. You can use this workspace to create your package. For reference you can create a new workspace with the following commands:

  ```bash
  mkdir -p ~/dev_ws/src
  cd ~/dev_ws/
  source /opt/ros/noetic/setup.bash
  export
  ```

## Exercises

Follow the tutorials in the links below. Complete the chapters listed under the heading.

Make sure that *ros_tutorials repo* has been previously created in github.

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

- [Creating a catkin package](http://wiki.ros.org/catkin/Tutorials/CreatingPackage) **Warning! catkin_ws should be changed to dev_ws**
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

## Assignment 1 - Due date January 13th, 11:59 pm (last git commit)

1. Create a GitHub profile [Github](https://github.com/).
2. Create a SSH key in your laptop [create-ssh-key](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-20-04) and add it in the github settings.
3. Create a repository named **ros_tutorials** - in order to play with some text files, and reproduce some working flow, for instance the one studied in the classroom.
4. Add a Description: This is the repository which is going to be used by the student during the Subject Software II, Introduction to ROS.
5. Make it Public
6. Check the box _Add a README file_.
7. Add Python .gitignore
8. Choose a MIT License.
9. Clone your repository: `cd ~/dev_ws/src` and  `git clone <your repository>` inside
10. Pull your repository `git pull`.
11. Configure the user and the mail as the ones previously configured when created the github profile,
12. Open vscode: `code .` document what are you doing in the wiki or Readme.md, telling what are you learning.
14. Push your repository:
  - `git add Readme.md`
  - `git commit -m “This is my first commit”`
  - `git push`
14. Make sure that all the files has been uploaded to github - enter to your profile and see that it matches with all the files that you have locally.
15. Find out other students of the master at GitHub and follow them.
15. Provide your name and link of repository [here](https://docs.google.com/spreadsheets/d/1ZyUKA4EDKNS-r1ppWnJ4YpjnhbGrnDkWbXj30VyRfmM/edit?usp=sharing).

## Assignment 2 - Due date January 13th 2024, 11:59 pm (last git commit)
0. Things to take into account before start the assignment:
  - Open a terminal
  - _note_: **catkin_ws** should be renamed to **dev_ws** and **distro** should be renamed to **noetic**.
  - source to ros `source /opt/ros/noetic/setup.bash`
  - navigate to the ros tutorials folder `cd ~/dev_ws/src/ros_tutorials`
1. Follow the tutorials at [ROS tutorials](http://wiki.ros.org/ROS/Tutorials):
  - Tutorial 1
  - Tutorial 2: Navigating the ROS Filesystem
  - Tutorial 3: Creating a ROS package
  - Tutorial 4: Building a ROS package
  - Tutorial 5: Understanding ROS Nodes
  - Tutorial 6: Understanding ROS Topics
  - Tutorial 7: Understanding ROS Services and Parameters
  - Tutorial 8: Using rqt_console and roslaunch
  - Tutorial 9: Using rosed to edit files in ROS
  - Tutorial 10: Creating a ROS msg and srv
  - Tutorial 12: Writing a simple Publisher and Subscriber (Python)
  - Tutorial 12: Examining Simple Publisher and Subscriber
  - Tutorial 13: Writing a Simple  Service and  Client (Python).
  - Tutorial 14: Examining Simple Service and Client.
  - Tutorial 15: Recording and playing back data.
  - Tutorial 16: Recording messages from a bag file
2. Add all files created to **ros_tutorial** github repository: git add *  or git add <file>
3. `git status`. If all packages are green, proceed to the next step. If not, add again the red ones.
4. git commit -m <add some info regarding the packages that you are adding>
5. git push
6. Go to your repository via website, and check that the remote branch is the same as the one that you have in your computer.

## References

- [ROS tutorials](http://wiki.ros.org/ROS/Tutorials)
- [ROS video tutorials - ROS Noetic for beginners](https://www.youtube.com/playlist?list=PLLSegLrePWgIbIrA4iehUQ-impvIXdd9Q)
- [learn python in ~75 min](https://youtu.be/VchuKL44s6E?feature=shared)
