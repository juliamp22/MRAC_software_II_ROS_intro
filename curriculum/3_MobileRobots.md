### fork and clone repo

1. create a new workspace:
`mkdir -p ~/dev_ws/src`
`cd ~/dev_ws/src`
2. Fork the repository from [here](git@github.com:roboticswithjulia/turtlebot_sim.git) 
3. Download the turtlebot_sim package [turtlebot_sim] cloned from your recently forked repository.
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

In vs code go to the Docker tab in the side bar. Right click on the container named turtlebot_sim:latest. Select attach vscode.

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

 1. Open a terminal, source to source the ws `/dev_ws/devel/setup.bash` and launch the main turtlebot simulation:
 `roslaunch turtlebot_gazebo turtlebot_world.launch`
 2. Open another terminal, source the ws `source /dev_ws/devel/setup.bash` and launch the amcl :
 `roslaunch turtlebot_gazebo amcl_demo.launch`
3. Open a third terminal, source the ws `source /dev_ws/devel/setup.bash` and launch the rviz :
  `rviz`, see that rviz opens.
 

 Go to file commander/notebooks/commander_examples.ipynb &rarr; double click and start to run the simulation.

 Make sure that the kernel is Started (Python 3.8.10) and start to execute the different codes.


#### Saving

Before closing the terminal you ran the docker image from remember to commit and push your changes.

## Assignment 1 (Due date 19th January 23:59)

1. Upload a video with the robot moving along the gazebo and rviz sending goals using the rviz gui.

## Assignment 2 (Due date 19th January 23:59)

Create a node (python executable) inside the **commander_move_base** package and implement the following:
 - Create a new node named **turtlebot_mover** which makes the robot move along three diferent positions with reference to the map. Make sure that the robot reaches the predefined positions getting the feedback from the robot.
 - Create a new node named **turtlebot_approx** which make the robot move with the velocity topic  '/mobile_base/commands/velocity' getting info from the lidar (/scan) being able to getting closer to a specific object and make the robot stop when the it is about 0.30m.
 - Add the overall nodes to the repository.
Create a new folder inisde the repository named *video*, add the video from the previous assignment.


