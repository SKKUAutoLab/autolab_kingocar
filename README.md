# ROS2 실습 가이드: 자동차 개조부터 파이썬으로 자율주행까지
</br>
</br>

## 1. Initial Setup

#### 1.1 Installation

```
sudo apt update
sudo apt upgrade -y
sudo apt install git
sudo apt install python-pip -y
pip install setuptools==58.2.0
```

만약 아래와 같은 에러가 발생한다면, `sudo apt install python3-pip` 명령어를 실행
```
Command 'pip' not found, but can be installed with:
sudo apt install python3-pip
```

pip을 올바르게 설치한 후, 아래 명령어를 실행
```
pip install setuptools==58.2.0
sudo pip install pyserial
sudo pip install keyboard
pip install opencv-python
pip install ultralytics
```
---

#### 1.2 Cloning
```
cd
git clone https://github.com/SKKUAutoLab/autolab_kingocar ros2_ws
cd ros2_ws
```
---

#### 1.3 Building
```
source /opt/ros/humble/setup.bash
rosdep install -i --from-path src --rosdistro humble -y
colcon build --symlink-install
```
---

</br>
</br>
</br>

## 2. Executing ROS2 Nodes

#### 2.1 Configure Environment
ROS2 노드를 실행하기 전에 각 터미널에 아래 명령어를 실행하여 환경 설정
```
cd ~/ros2_ws
source /opt/ros/humble/setup.bash
source install/local_setup.bash
```
---


#### 2.2 Node Execution
각 터미널에서 아래 명령어를 하나씩 실행하여 노드 실행
```
ros2 run load_img cam_pub
```
```
ros2 run yolov8_ros predict
```
```
ros2 run img_process img_post
```
```
ros2 run img_process img_grad
```
```
ros2 run control_motor gen_control_data
```
```
ros2 run control_motor convert_protocol
```
```
ros2 run control_motor send_serial 
```



