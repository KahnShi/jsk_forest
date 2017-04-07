# jsk_forest

### 1. Installation

The system is tested with Ubuntu 16.04 and ROS Kinetic.

For indigo version, there is high possibility that problem happens (old version of gazebo, boost, etc).

Currently, there are 2 available quadrator model, hector and AesTech Firefly (ETH).

#### 1). Hector

Build hector_quadrotor package

```
cd ~/catkin_ws/src
git clone https://github.com/tu-darmstadt-ros-pkg/hector_quadrotor
cd hector_quadrotor/hector_quadrotor
catkin bt
```

Launch the system and simulator

```
roslaunch jsk_forest_simulation trajectory_replanning_simulation.launch has_hector:=true
```

#### 2). AesTech Firefly

Build rotors_simulator package

```
cd ~/catkin_ws/src
git clone https://github.com/ethz-asl/rotors_simulator.git
cd rotors_simulator
git checkout bf3f59
cd rotors_simulator
catkin bt

git clone https://github.com/ethz-asl/mav_comm.git
cd mav_comm
git checkout eae7c76
cd mav_comm
catkin bt
```

Launch the system and simulator

```
roslaunch jsk_forest_simulation trajectory_replanning_simulation.launch has_hector:=false
```


### 2. Acknowlegement

Simulator is based on:
* **Real-Time Trajectory Replanning for MAVs using Uniform B-splines and 3D Circular Buffer**, V. Usenko, L. von Stumberg, A. Pangercic, D. Cremers, In [arXiv:1703.01416](https://arxiv.org/abs/1703.01416), 2017

For more information about origin full package, see
[https://github.com/vsu91/ewok](https://github.com/vsu91/ewok)
