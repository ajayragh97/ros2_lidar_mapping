# ros2_lidar_mapping

# Instructions

## Docker 

The docker container is setup with ros2 humble, turtlebot3 and gazebo installed.

### Building the docker image

Navigate to the directory **humble** and open a terminal here.
Run the command:

```docker build -t humble .```

This will create a docker image called humble in your system.

### Launching the container

Now once the docker image is built, the container can be launched by running the command:

```make up```

This will run the container. Now to enter the container run the following command:

```make enter```

Now you have access to the container running on ubuntu jammy and ros2 humble, installed with gazebo and turtlebot3.

### Launching Turtlebot3

Now launch a turtlebot3 simulation using the command:

```ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py```

By default the **burger** model of turtlebot will be spawned. If you want to change the model run:

```export TURTLEBOT3_MODEL=burger```

Change value ***burger*** to your desired model. 

**Note: Currently only the burger model is being spawned. The waffle and waffle_pi models are not being spwned and are giving errors as of now.**

# Changelog

## Version 0.1
**Updates**: Created docker container with ros2 humble and turtlebot3+gazebo. 