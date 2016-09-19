# Kulbabu

A basic ROS implementation with Gazebo simulation.

* Utilises `diff_drive_controller`.
* `kulbabu_hardware` implements ultrasonic sensors.

## install

```
wstool merge https://raw.githubusercontent.com/kulbu/kulbabu/kinetic-devel/kulbabu.rosinstall -t src

# Optional:
wstool merge https://raw.githubusercontent.com/kulbu/kulbabu/kinetic-devel/kulbabu_sim.rosinstall -t src
wstool merge https://raw.githubusercontent.com/kulbu/kulbabu/kinetic-devel/kulbabu_real.rosinstall -t src
```

## Build

```
wstool update -t src
rosdep update
rosdep install --from-paths src --ignore-src --rosdistro kinetic -y --os $(lsb_release -si | awk '{print tolower($0)}'):$(lsb_release -sc))
catkin build
```

## Usage

```
roslaunch kulbabu_base sim.launch
roslaunch kulbabu_base real.launch
rosrun turtlebot_teleop turtlebot_teleop_key /turtlebot_teleop/cmd_vel:=/kulbabu/diff_drive_controller/cmd_vel
```

```

## Hardware

* https://github.com/kulbu/kulbabu_hardware
