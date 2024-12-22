# Robot Overview

![Robot1](./resources/2024-12-22%2015.40.23.jpg)
![Robot2](./resources/2024-12-22%2015.40.12.jpg)

## Pre-requisit
- ROS2 Hummble

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


## Software modules

### Active
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

