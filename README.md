# RoboND-Map-My-World
This is a repository for mapping of a 3D world in Gazebo using RTABMap slam package in ROS1 Noetic 

![Screenshot from 2024-07-27 16-47-50](https://github.com/user-attachments/assets/e201cc56-3515-4cbf-9647-5841f5a42c04)

## Prerequisites

Ensure you have the following installed and set up:
- ROS Noetic
- Gazebo
- Rviz
- RTABMap and RTABMap ROS package
   ```sh
    $ sudo apt-get install rtabmap_ros rtabmap
   ```
- Teleop Twist Keyboard ROS Package
  ```sh
    $ sudo apt-get install ros-noetic-teleop-twist-keyboard
   ```
- Your custom SLAM project located at `~/catkin_ws/src/slam_project`


## Steps to Launch RTABMap for SLAM

### 1. Launch the Gazebo World and Your Robot

To launch your Gazebo world and robot, run the following command:

```sh
  $ roslaunch slam_project world.launch world_file:=~/catkin_ws/src/slam_project/worlds/kitchen_dining.world

```

### 2. Launch Teleop Node

To launch your Gazebo world and robot, run the following command:

```sh
  $ rosrun teleop_twist_keyboard teleop_twist_keyboard.py

```

### 3. Launch Rviz

To launch your Gazebo world and robot, run the following command:

```sh
  $ roslaunch slam_project rviz.launch

```

### 4. Launch mapping.launch file for mapping

To launch your Gazebo world and robot, run the following command:

```sh
  $ roslaunch slam_project mapping.launch

```

## Steps to save Map

#### 1. Roam around the entire world to take clear pictures of world and should have around 3 Loop closures

#### 2. The Database gets saved after closing mapping.launch file

#### 3. You can view your map in using RTABMap Database Viewer  
```sh
  rtabmap-databaseViewer ~/.ros/rtabmap.db
```
#### 4. To view the 3D map:
  - Open RTABMap Database Viewer
  - Press “Edit” on the top bar
  - Press “View 3D Map”
  - You need to change the max no. of Particles inorder to see a clear 3D map

#### 5. Downlaod the Map
  - Open File
  - Download 3d map

## References 
- Udacity Robotics Nanodegree
- https://dabit-industries.github.io/turtlebot2-tutorials/07b-RTABMAP.html



