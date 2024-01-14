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
