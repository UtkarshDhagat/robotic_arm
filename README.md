# 🤖 Robot Arm - ROS Noetic + Gazebo Simulation

A ROS Noetic package for simulating, controlling, and testing a 6-DOF robotic arm (with gripper) in **Gazebo**.  
Includes **URDF model**, **Gazebo controllers**, and **Python control nodes** for manual and programmatic arm control.

---

## 📌 Features
- **URDF Model** with links, joints, and transmissions
- **Gazebo Simulation** with ROS Control integration
- **Position Controllers** for all arm joints and grippers
- **Python Command Node** for interactive control via terminal
- **Joint State Publisher Node** for streaming joint positions

---

## 📂 Project Structure
```

robot\_arm/
├── CMakeLists.txt
├── package.xml
├── urdf/
│   └── mybot.urdf
├── yaml/
│   └── controllers.yaml
├── scripts/
│   ├── move\_arm.py
│   └── joint\_state\_publisher.py
├── launch/
│   └── arm\_simulation.launch

````

---

## 🔧 Dependencies
Ensure you have the following installed:
- [ROS Noetic](http://wiki.ros.org/noetic/Installation)
- Gazebo (comes with ROS Desktop-Full)
- `rospy`
- `std_msgs`
- `trajectory_msgs`
- `controller_manager`
- `gazebo_ros`

Install missing dependencies:
```bash
sudo apt install ros-noetic-joint-state-publisher ros-noetic-position-controllers ros-noetic-controller-manager ros-noetic-gazebo-ros
````

---

## 🚀 Installation & Build

1. Clone into your ROS workspace:

```bash
cd ~/catkin_ws/src
git clone https://github.com/yourusername/robot_arm.git
```

2. Build the workspace:

```bash
cd ~/catkin_ws
catkin_make
source devel/setup.bash
```

---

## ▶️ Run Simulation

To launch the robotic arm in **Gazebo**:

```bash
roslaunch robot_arm arm_simulation.launch
```

This will:

* Load the **URDF** model
* Start an empty Gazebo world
* Spawn the robot
* Load and start controllers

---

## 🎮 Controlling the Arm

### 1️⃣ Interactive Terminal Control

Run:

```bash
rosrun robot_arm move_arm.py
```

Available commands:

* `move` → Set all joint positions
* `change` → Change only one joint position
* `release` → Open gripper
* `close` → Close gripper
* `stop` → Reset to initial position

Example:

```
Enter : move
hip position : 0.5
shoulder position : 0.3
elbow position : -0.5
wrist position : 0.2
```

---

### 2️⃣ Publish Joint States

Run:

```bash
rosrun robot_arm joint_state_publisher.py
```

This continuously publishes joint positions to `/joint_states`.

---

## 🛠 File Highlights

* **`mybot.urdf`** → Full URDF model of the arm
* **`controllers.yaml`** → Joint trajectory controller config
* **`move_arm.py`** → Interactive movement control
* **`joint_state_publisher.py`** → Publishes joint states programmatically
* **`arm_simulation.launch`** → Launches Gazebo simulation with controllers

---

## 📜 License

This project is licensed under the **MIT License**.

---


