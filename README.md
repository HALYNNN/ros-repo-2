# 📌 My Role & Key Contributions (장하린)

> **애드인에듀 AI 로봇 자율주행 FINAL PROJECT** · 2024.04.17 ~ 2024.06.13 · 6명 · 🏆 **최우수상** (2024.06.14)
>
> 이 레포지토리는 6인 팀 프로젝트입니다. 아래는 그중 **장하린**이 담당한 역할과 트러블슈팅을 정리한 것이며, 팀 전체 README는 이 섹션 아래에 원문 그대로 보존했습니다.

## 담당 역할

- **SLAM 맵핑** — LiDAR·카메라 센서로 환경 데이터를 수집하고 로컬 맵 생성
- **DB 구축 및 통합 관리** — MySQL로 로봇 상태·작업 기록 DB를 구축하고 ROS2 실시간 데이터 연동
- **관제 GUI 개발** — PyQt5 기반 소비자(주문·재고)·관리자(관제·로봇 위치/충돌/작업 내역) GUI 구현
- **모듈 간 송수신 검증** — Robot(지게차형 AMR 3대) ↔ Server(Task Allocator, ROS Bridge WebSocket, Domain Bridge, MySQL) ↔ Client(GUI) 간 연동 검증 및 오류 수정

## 핵심 트러블슈팅

### 1. 실시간 위치 표시 중 PyQt GUI 화면 멈춤·크래시 해결

- **문제** — ROS2 → WebSocket → PyQt GUI로 데이터를 갱신하는 과정에서 화면 프리징이 발생
- **원인 분석** — 단순 전송 주기(Hz) 조정으로는 스레드 간 간섭(Race Condition)이 해결되지 않음을 확인
- **해결** — QObject 기반 `SignalEmitter` 클래스와 `pyqtSignal`로 비동기 수신 데이터를 메인 스레드에 안전하게 전달하도록 구조 개선
- **결과** — 프리징·크래시 해소 및 갱신 안정화

## 시연 영상

▶ [최종 시연 영상 보기](https://youtu.be/72EWf1t_NVw) — https://youtu.be/72EWf1t_NVw

---

# AMR Logistics Automation System
<div align="center">
    <img src="https://github.com/addinedu-ros-4th/ros-repo-2/assets/118419026/dd1da530-6c66-4815-94ef-1b23f385e5c4" width="700" height="300">
</div>


<div align="center">

| [![Video 4](https://img.youtube.com/vi/72EWf1t_NVw/sddefault.jpg)](https://youtu.be/72EWf1t_NVw) |
|:---:|
| [최종 시연 영상](https://youtu.be/72EWf1t_NVw) |

</div>

## 1. 🤖Project Introduction
**Duration: 2024.04.17 - 2024.06.13**

### 1.1. Project Overview
- Utilizing forklift frame-based autonomous driving robots in logistics processes such as inbound, outbound, and collection.
- Implementing a multi-robot control system to enhance the efficiency of logistics operations.
- Optimizing logistics center operations through Human-Robot Interaction (HRI).
- Implementing systems for inbound product registration, shelf inventory management, and consumer order processing.

<img src="https://github.com/addinedu-ros-4th/ros-repo-2/assets/61307553/bd473944-faa3-45ad-8b47-0333070b8721">

### 1.2. Project Position
<table>
  <thead>
    <tr>
      <th style="text-align:center;">Name</th>
      <th style="text-align:center;">Classification</th>
      <th style="text-align:center;">Role</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:center;">YONG TAK SONG</td>
      <td style="text-align:center;">Team Leader</td>
      <td>- Robot System Integration and Control <br> - Robot Mechanism Design <br> - SLAM & NAV <br> - Architecture and Algorithm Design <br> - Setting up Driving Environment <br> - Detailed Feature Improvement and Code Integration </td>
    </tr>
    <tr>
      <td style="text-align:center;">DONG GYU KIM</td>
      <td style="text-align:center;">Team Member</td>
      <td>- ArUco Navigation <br> - DL based Human Following Robot <br> - Analysis User/System Requirement <br> - Architecture and Algorithm Design <br> - Setting up Driving Environment <br> - Confluence Management </td>
    </tr>
    <tr>
      <td style="text-align:center;">KYEOM HEE YOU</td>
      <td style="text-align:center;">Team Member</td>
      <td>- SLAM <br> - Admin GUI <br> - Database Construction
 <br> - Setting up Driving Environment  </td>
    </tr>
    <tr>
      <td style="text-align:center;">JEA HYUCK LEE</td>
      <td style="text-align:center;">Team Member</td>
      <td>- SLAM & NAV <br> - Path Planning Algorithm Design <br> - Multi-Robot Control System Implementation <br> - Detailed Feature Improvement and Code Integration <br> - Setting up Driving Environment  </td>
    </tr>
    <tr>
      <td style="text-align:center;">HA RIN JANG</td>
      <td style="text-align:center;">Team Member</td>
      <td>- SLAM <br> - Admin GUI <br> - User GUI
 <br> - Database Construction </td>
    </tr>
    <tr>
      <td style="text-align:center;">GA EUN CHOI</td>
      <td style="text-align:center;">Team Member</td>
      <td>- Multi-Robot Task Handling <br> - Communication Interface and Protocol Design <br> - Robot Communication Server Construction <br> - GitHub and Jira Management </td>
    </tr>
  </tbody>
</table>




### 1.3. Tech Stack
||||
|:---:|:---|:---|
|**Develop EnV**|<img src="https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=Ubuntu&logoColor=white"> <img src="https://img.shields.io/badge/VISUAL STUDIO CODE-007ACC?style=for-the-badge&logo=VisualStudioCode&logoColor=white">|
|**TECH**|<img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54"> <img src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white"> <img src="https://img.shields.io/badge/ros2-%2322314E?style=for-the-badge&logo=ros&logoColor=white"> <img src="https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white"> <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white"> <img src="https://img.shields.io/badge/PyQt5-%23217346.svg?style=for-the-badge&logo=Qt&logoColor=white"> <img src="https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white"> |
|**H/W**|<img src="https://img.shields.io/badge/-RaspberryPi 4-C51A4A?style=for-the-badge&logo=Raspberry-Pi"> <img src="https://img.shields.io/badge/-Arduino Mega-00979D?style=for-the-badge&logo=Arduino&logoColor=white">|
|**COMMUNICATION**|<img src="https://img.shields.io/badge/confluence-%23172BF4.svg?style=for-the-badge&logo=confluence&logoColor=white"> <img src="https://img.shields.io/badge/jira-%230A0FFF.svg?style=for-the-badge&logo=jira&logoColor=white"> <img src="https://img.shields.io/badge/Slack-4A154B?style=for-the-badge&logo=Slack&logoColor=white">  <img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white">|

<br>

## 2. 📋Project Design

### 2.1. System Architecture

<img src="https://github.com/addinedu-ros-4th/ros-repo-2/assets/61307553/22c544f1-22be-48fb-b88e-ad07626dc193">

### 2.2. Hardware Architecture
<img src= "https://github.com/addinedu-ros-4th/ros-repo-2/assets/61307553/6b327300-fc61-4389-8219-fb2ba5b60c00">

### 2.3. Software Architecture
<img src="https://github.com/addinedu-ros-4th/ros-repo-2/assets/61307553/561a7e3b-3354-4311-8aa6-33e57b93ff11">

<br>

## 3. 💡Technology

### 3.1. 3D Pose Estimation

#### 3.1.1. Camera Calibration
<img src= "https://github.com/addinedu-ros-4th/ros-repo-2/assets/61307553/ec978cc8-c120-4b81-80f5-11d6f1f13173">

#### 3.1.2. ArUCo Navigation
<img src= "https://github.com/addinedu-ros-4th/ros-repo-2/assets/61307553/227729b6-08ac-4aa4-8b59-4db3c9a46f73">

### 3.2. Human Following
<img src="https://github.com/addinedu-ros-4th/ros-repo-2/assets/61307553/bfbcab64-6ab8-4cc2-9e5f-e4d972ba74ee">

### 3.3 Path Planning
<img src="https://github.com/addinedu-ros-4th/ros-repo-2/assets/61307553/a725b3f2-d9cb-4e85-9145-db014f7f7748">

### 3.4 Task Allocator
<img src="https://github.com/addinedu-ros-4th/ros-repo-2/assets/61307553/f0b96a9c-c18c-4987-9fe7-ecac2deb2c50">

### 3.5 Robot Monitoring And Control System
<img src="https://github.com/addinedu-ros-4th/ros-repo-2/assets/61307553/beacb508-6174-4b2a-8812-68eb6de427e4">

<br>

## 4. ✅Prerequisite

**How to install ROS2 Humble on PC [Ubuntu 22.04]**
- Follow the guidelines within the site
    - environment : https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html
    - dev tools : https://docs.ros.org/en/humble/Installation/Alternatives/Ubuntu-Development-Setup.html#install-development-tools-and-ros-tools
    - colcon : https://docs.ros.org/en/humble/Tutorials/Beginner-Client-Libraries/Colcon-Tutorial.html#install-colcon

**ArUCo version on OpenCV**
```sh
pip install opencv-contrib-python==4.7.0.68 opencv-python==4.7.0.68
```

**Raspberry pi 4 GPIO settings**
```sh
# GPIO 그룹 설정
sudo groupadd gpio
# 사용자를 gpio 그룹에 추가
sudo usermod -aG gpio kkyu_rasp
# udev 규칙 파일 설정
sudo nano /etc/udev/rules.d/99-gpio.rules
# udev 규칙 내용 작성
SUBSYSTEM=="gpio*", PROGRAM="/bin/sh -c '\\
chown -R root:gpio /sys/class/gpio && chmod -R 770 /sys/class/gpio;\\
chown -R root:gpio /sys/devices/virtual/gpio && chmod -R 770 /sys/devices/virtual/gpio;\\
chown -R root:gpio /sys$devpath && chmod -R 770 /sys$devpath\\
'"
# udev 규칙 적용
sudo udevadm control --reload-rules
sudo udevadm trigger
sudo reboot now
```

**Raspberry pi 4 permission settings**
```sh
sudo chown root:gpio /dev/gpiomem
sudo chmod g+rw /dev/gpiomem
sudo chmod a+rw /dev/i2c-* 
```

**Raspberry pi 4 camera settings**
```sh
sudo chmod 777 /dev/video0
```

**Websocket Dependency**
```sh
pip install websocket-client
pip install PyQt5 websocket-client
```

**Others**
```sh
sudo apt install ros-humble-test-msgs
```

**.bashrc settings**
```sh
echo "Humble is activated.!"
source /opt/ros/humble/setup.bash
echo "Minibot is activated.!"
source ~/ros-repo-2/robot/install/local_setup.bash
echo "Server is activated.!"
source ~/ros-repo-2/server/install/local_setup.bash
echo "ROS_DOMAIN_ID is set 213"  # 각 로봇에 대한 ID : 213, 214, 215
export ROS_DOMAIN_ID=213

sudo chmod 777 /dev/video0
sudo chown root:gpio /dev/gpiomem
sudo chmod g+rw /dev/gpiomem
sudo chmod a+rw /dev/i2c-*
```

## 5. ⏩Usage

**General Setup**

```sh
git clone https://github.com/addinedu-ros-4th/ros-repo-2.git

cd ros-repo-2/robot
colcon build
source ./install/local_setup.bash

cd ../server
colcon build
source ./install/local_setup.bash
```

*- Recommend: Use the SSH method for remote access*
- ex) ssh -X your_rasp_name@your_rasp_ip
  
**Robot 1/2/3 PC (Raspberry Pi PC)**
- Domain ID : 91 / 92 / 93

```sh
# bringup robot : arduino (encoder motor) + Raspberry (YD LIDAR)
ros2 launch minibot_bringup bringup_robot.launch.py

# Aruco & Step motor (fork lift) Node
ros2 launch robot_aruco aruco_detect.launch.py

# human following mode
ros2 launch human_following following.launch.py
```

**Robot 1/2/3 PC (LOCAL PC)**
```sh
export ROS_DOMAIN_ID = 91 / 92 / 93

# check ROS_DOMAIN_ID SETTINGS
printenv grep -i ROS_DOMAIN_ID

source /opt/ros/humble/setup.bash
source ~/.bashrc

# Robot Controller
ros2 run robot_controller robot_controller

# slam toolbox + nav2 package
ros2 launch minibot_navigation2 bringup_launch.py map:=`ros2 pkg prefix minibot_navigation2`/share/minibot_navigation2/maps/re_map.yaml

# rviz visualization
rviz2 -d `ros2 pkg prefix minibot_navigation2`/share/minibot_navigation2/rviz/nav2_view.rviz
```

**Server**
```sh
export ROS_DOMAIN_ID = 90
source /opt/ros/humble/setup.bash
source ~/.bashrc

# websocket bridge
ros2 launch rosbridge_server rosbridge_websocket_launch.xml

# ros2 domain bridge
ros2 run domain_bridge domain_bridge ~/your_path/server/config/bridge_config.yaml

# task allocator server
ros2 launch task_manager task_manager_launch.py
```

**Consumer GUI**
```sh
(venv) (root folder) python3 gui/consumer/src/ui_main.py
```

**Manager GUI**
```sh
(inside gui folder) ros2 run manager.pkg manager_main.py
```

**Robot test Service**
```sh
# aruco control service call
# location : I1,I2,I1 / O1,O2,O3 / P1,P2,P3 / R1,R2 / A1,A2 / B1,B2 / C1,C2
# direction : forward, backward
ros2 service call /aruco_control task_msgs/srv/ArucoCommand "{location: O1, direction: forward}"

# step control service call
# floor : 1,2
# direction : up, down
ros2 service call /step_control task_msgs/srv/StepControl "{floor: 2, direction: up}"

# camera control service call
# data : True / False
ros2 service call /camera_control std_srvs/srv/SetBool "{data: True}"
```

**Server test Service**
```sh
# waypoint move service call
# location : I1,I2,I1 / O1,O2,O3 / P1,P2,P3 / R1,R2 / A1,A2 / B1,B2 / C1,C2
# lift : Up, Down
ros2 service call /allocate_task_92 task_msgs/srv/AllocateTask "{location: "I2", lift: 'Up'}"
```

| [![Video 1](https://img.youtube.com/vi/8Qt1J9MkPb4/sddefault.jpg)](https://youtu.be/8Qt1J9MkPb4) | [![Video 2](https://img.youtube.com/vi/RSHB1A6I8J8/sddefault.jpg)](https://youtu.be/RSHB1A6I8J8) |
|:---:|:---:|
| <div align="center">[ArUCo 3D Pose Estimation](https://youtu.be/8Qt1J9MkPb4)</div> | <div align="center">[Human Following Robot](https://youtu.be/RSHB1A6I8J8)</div> |
