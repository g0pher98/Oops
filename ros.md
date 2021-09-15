# #1
```
The program 'roscore' is currently not installed. You can install it by typing:
sudo apt install python-roslaunch
```
ROS를 처음 설치했을 때, 뜨는 오류. 친절하게 설치하라고 알려주지만, 스크립트 실행 후 `~/.bashrc`가 실행되지 않아서 발생한 문제였다.
```
source ~/.bashrc
```

# #2
```
$ rosrun rqt_graph rqt_graph
Traceback (most recent call last):

...

ModuleNotFoundError: No module named 'rospkg'
```
`.bashrc`에 있는 Anaconda 설정 내용이 ros 설정과 충돌을 일으켜서 발생한 문제다. `.bashrc`에서 anaconda 설정 부분만 다른 sh 파일로 만들어놓고 사용하는게 좋을 것 같다.

# #3
```
Traceback (most recent call last):
  File "/home/cgp/catkin_ws/src/rbx1/rbx1_nav/nodes/runopencv.py", line 3, in <module>
    import rospy
  File "/opt/ros/melodic/lib/python2.7/dist-packages/rospy/__init__.py", line 49, in <module>
    from .client import spin, myargv, init_node, \
  File "/opt/ros/melodic/lib/python2.7/dist-packages/rospy/client.py", line 52, in <module>
    import roslib
  File "/opt/ros/melodic/lib/python2.7/dist-packages/roslib/__init__.py", line 50, in <module>
    from roslib.launcher import load_manifest
  File "/opt/ros/melodic/lib/python2.7/dist-packages/roslib/launcher.py", line 42, in <module>
    import rospkg
ModuleNotFoundError: No module named 'rospkg'
```
`rosrun`을 진행하던 중 발생한 오류. 우선 python 버전부터 확인하고, 작업하던 버전이 맞는지 확인해야한다. ros가 원하는 버전의 파이썬으로 스크립트를 실행하지 않는다면 코드 상단에 아래와 같이 명시해주면 된다.
``` python
#!/usr/bin/env python
```

만약 버전이 맞는데도 실행이 안된다면 다음과 같이 설치해주면 된다.
``` bash
sudo apt install python-pip
```