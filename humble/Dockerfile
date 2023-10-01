FROM ros:humble-perception

ENV WS_DIR="/home/ros2_ws"
WORKDIR ${WS_DIR}

SHELL ["/bin/bash", "-c"]

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update -y \
 && apt-get install -y \
    build-essential \
    cmake \
    git-all \
    software-properties-common

RUN apt-get update -y \
 && apt install ros-humble-tf-transformations \
 && apt-get update -y \
 && apt-get install -y \
    ros-humble-rviz2\ 
 && mkdir src \
 && cd src \
 && cd .. \
 && apt-get install -y python3-rosdep \
 && source /opt/ros/${ROS_DISTRO}/setup.bash \
 && rm /etc/ros/rosdep/sources.list.d/20-default.list \
 && rosdep init \
 && rosdep update \
 && colcon build \
 && apt install -y gazebo \
 && apt install -y ros-humble-gazebo-ros-pkgs \
 && apt install -y ros-humble-cartographer \
 && apt install -y ros-humble-cartographer-ros \
 && apt install -y ros-humble-navigation2 \
 && apt install -y ros-humble-nav2-bringup \
 && cd src \
 && git clone https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git -b humble-devel \
 && git clone https://github.com/ROBOTIS-GIT/turtlebot3.git -b humble-devel \
 && git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git -b humble-devel \
 && git clone https://github.com/ROBOTIS-GIT/DynamixelSDK.git -b humble-devel \
 && cd .. \
 && colcon build \
 && touch /home/.bashrc \
 && echo 'source /opt/ros/humble/setup.bash' >> ~/.bashrc \
 && echo 'source /home/ros2_ws/install/setup.bash' >> ~/.bashrc \
 && echo 'export TURTLEBOT3_MODEL=burger' >> ~/.bashrc \
ARG DEBIAN_FRONTEND=dialog