# Robot overview

![Robot1](./resources/2024-12-22%2015.40.23.jpg)
![Robot2](./resources/2024-12-22%2015.40.12.jpg)

## Hardware

- 2-wheel differencial drive robot
  - Motor drive: https://www.amazon.co.jp/dp/B083DT2DMV?ref=ppx_yo2ov_dt_b_fed_asin_title
  - Photo encoder: https://www.amazon.co.jp/dp/B084VP1GXS?ref=ppx_yo2ov_dt_b_fed_asin_title
  - Motor, chasis, tires
- Computer
  - Raspberry pi 4B 8GB: https://www.amazon.co.jp/dp/B09G376N9L?ref=ppx_yo2ov_dt_b_fed_asin_title
- Lidar
  - Rplidar A1M8: https://www.amazon.co.jp/gp/product/B07ZD4ML34/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1
- IMU
  - Yahboom 10-Axis IMU: https://www.amazon.co.jp/dp/B0CBM1SKCZ?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1
- Front camera
  - Buffalo BSW505MBK: https://www.amazon.co.jp/dp/B07YWDP7PD?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1
- Battery
  - Elecom mobile battery: https://www.amazon.co.jp/dp/B0CTZG7Q8Q?ref=ppx_yo2ov_dt_b_fed_asin_title
- Game pad  
  - Logicool G F710R: https://www.amazon.co.jp/dp/B00CDG7994?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1

## Software modules

### Pre-requisites
- ROS2 Humble

### Active modules
- Robot controller
  - https://github.com/kenyam1979/robot_controller
- Lidar
  - https://github.com/Slamtec/sllidar_ros2
- IMU
  - http://www.yahboom.net/study/IMU
  - (Fixed vervion) https://github.com/kenyam1979/wit_ros2_imu_fixed
- Robot description for state publisher
  - https://github.com/kenyam1979/robot_description
- Nav2 config
  - https://github.com/kenyam1979/robot_navigation

### Work in progres
- Autonomous Emergency Braking
  - https://github.com/kenyam1979/robot_aeb

- Camera publisher
  - https://github.com/kenyam1979/robot_camera

### Discontinued
- Interface definition
  - https://github.com/kenyam1979/robot_interfaces


## How to run




### 1. Initiate the robot controller
Ssh to RaspberryPi, and move to ros work space, then run:
```
sudo pigpiod
ros2 run robot_controller motor_controller
```

### 2. (Optional) Initiate Teleo
```
ros2 launch robot_controller teleop_launch.py config_filepath:=/home/ken/ros2_ws/src/robot_controller/config/ps3.config.yaml 
```

### 3. Initiate the Ridar 
```
ros2 launch sllidar_ros2 sllidar_a1_launch.py 
```

### 4. Initiate the IMU
```
ros2 launch wit_ros2_imu rviz_and_imu.launch.py
```

### 5. Initiate the robot state publisher
```
ros2 launch robot_description robot.launch.py
```

### 6. Initiate Nav2
```
ros2 launch nav2_bringup bringup_launch.py use_sim_time:=False map:=/home/ken/ros2_ws/src/robot_navigation/map/myroom_20240817.yaml params_file:=/home/ken/ros2_ws/src/robot_navigation/config/costmap_param.yaml 
```
*Please change the map file name accordingly. The map file can be created by async SLAM mode.

### 7. Run rviz
Open laptop on the same network with the raspberryPi and run:
```
ros2 launch robot_description display.launch.py
```