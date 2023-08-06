# Robotics-and-AI-Department-Task-2
2nd task of Robotics and AI Department Department - Summer training program at Smart Methods

![ROS AI Path task 2](https://github.com/H16Bw/Robotics-and-AI-Department-Task-2/assets/139852537/f5df83e8-f18c-4382-82cb-5da7e5373d3c)


# Learning ROS through simulation with TurtleBot3 and Gazebo involves several steps:

1. Install ROS: Begin by installing ROS on your computer. Follow the ROS wiki's instructions to install the appropriate version for your operating system.

2. Install TurtleBot3 and Gazebo: After installing ROS, proceed to install the TurtleBot3 and Gazebo packages.

3. Launch the simulation: Once TurtleBot3 and Gazebo are installed, you can launch a simulation environment by running a launch file. This file sets up the simulation and starts the necessary nodes.

4. Develop and test your code: With the simulation environment running, you can start developing and testing your ROS code. Use tools like RViz to visualize the robot and its surroundings, and simulate sensors like cameras and lidars using Gazebo.

5. Iterate and refine: As you develop your code, iteratively refine it based on the simulation results. Experiment with different algorithms and approaches without risking physical robots.

## Installation Steps:

1. Install core dependencies: Install ROS packages necessary for controlling the TurtleBot. Execute the following command in the terminal:

```
sudo apt install ros-noetic-joy ros-noetic-teleop-twist-joy \
  ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc \
  ros-noetic-rgbd-launch ros-noetic-depthimage-to-laserscan \
  ros-noetic-rosserial-arduino ros-noetic-rosserial-python \
  ros-noetic-rosserial-server ros-noetic-rosserial-client \
  ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
  ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
  ros-noetic-compressed-image-transport ros-noetic-rqt* \
  ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers \
  ros-noetic-gazebo-ros-pkgs
```

2. Install additional packages: Install packages for the TurtleBot's servo actuators (motors) and main communication messages:

```
sudo apt install ros-noetic-dynamixel-sdk
sudo apt install ros-noetic-turtlebot3-msgs
```

3. Install TurtleBot3: Install the main TurtleBot3 package:

```
sudo apt install ros-noetic-turtlebot3
```

4. Install TurtleBot3 Simulations: Clone the TurtleBot3 Simulations package from Git into the Catkin Workspace and run `catkin_make`:

```
cd ~/catkin_ws/src/
git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
cd ~/catkin_ws && catkin_make
```

5. Set up environment variables: Edit the `.bashrc` file to define the correct variables every time a new terminal opens:

```
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
source ~/.bashrc
```

## Starting the Simulation:

1. Launch Gazebo world: Choose your desired Gazebo world for experimentation.

2. Run SLAM node: Use the SLAM node to create a map:

```
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```

3. Launch teleoperation node: Enable driving the robot and collecting sensor data to create a map:

```
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```

Now you are ready to learn ROS through simulation with TurtleBot3 and Gazebo. Experiment, develop, and refine your code in this simulated environment before deploying it to physical robots.
