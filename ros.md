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