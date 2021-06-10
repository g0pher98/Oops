# #1
```
The program 'roscore' is currently not installed. You can install it by typing:
sudo apt install python-roslaunch
```
ROS를 처음 설치했을 때, 뜨는 오류. 친절하게 설치하라고 알려주지만, 스크립트 실행 후 `~/.bashrc`가 실행되지 않아서 발생한 문제였다.
```
source ~/.bashrc
```