# MCT443s: Autonomous Mobile Robot (AMR)
<p align="center">
  <img src="cover.png" alt="MCT443s Autonomous Mobile Robot Banner" width="100%">
</p>

# MCT443s: Autonomous Mobile Robot (AMR)
A complete ROS2-based Autonomous Mobile Robot system designed, simulated in Gazebo, and deployed on custom hardware for the **MCT443s Design of Autonomous Systems** course project[cite: 1, 3, 4].

## 📌 Project Tasks
1. **Task 1 (Lane Following):** Autonomous center-lane tracking and heading stabilization along a 10m straight single-lane track (40 cm width) using computer vision and IMU feedback[cite: 2].
2. **Task 2 (Obstacle Avoidance & Lane Switching):** Navigating a 10m two-lane road (40 cm per lane) by detecting static obstacles at 4m (right lane) and 8m (left lane) and executing smooth lane switches without crossing boundary lines[cite: 2, 3].

## 🛠️ System Architecture & Hardware
* **Vehicle Platform:** 4-wheeled / Rear-wheel drive mobile robot (< 30 cm width)[cite: 2]
* **Processing Unit:** [Raspberry Pi / Jetson Nano / ESP32 + Laptop][cite: 2]
* **Sensors:** RGB Camera (lane detection), IMU (orientation), Ultrasonic/LIDAR (obstacle detection), Wheel Encoders (odometry)[cite: 2]
* **Software Stack:** ROS2 [Humble/Jazzy], Gazebo, OpenCV, Python/C++, MATLAB/Simulink *(Optional)*[cite: 1, 3]

## 📂 Repository Structure
* `ros2_ws/src/amr_description`: URDF/Xacro robot model and sensor configurations[cite: 3].
* `ros2_ws/src/amr_gazebo`: Simulation worlds for Task 1 and Task 2[cite: 3, 5].
* `ros2_ws/src/amr_perception`: Camera-based lane detection and obstacle detection nodes[cite: 3].
* `ros2_ws/src/amr_localization`: Odometry and IMU sensor fusion[cite: 3].
* `ros2_ws/src/amr_control`: Lateral/longitudinal controllers (PID/Pure Pursuit/Stanley) and lane-switching logic[cite: 3].
* `ros2_ws/src/amr_hardware`: Low-level motor driver and physical sensor interfaces[cite: 4].
* `ros2_ws/src/amr_bringup`: Launch files for simulation and hardware execution[cite: 5].
* `matlab_simulink`: Mathematical modeling and controller simulation scripts[cite: 4].

## 🚀 How to Run

### 1. Build the Workspace
```bash
cd ros2_ws
colcon build --symlink-install
source install/setup.bash
