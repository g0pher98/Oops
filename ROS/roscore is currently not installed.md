#   'roscore' is currently not installed
```
The program 'roscore' is currently not installed. You can install it by typing:
sudo apt install python-roslaunch
```
친절하게 설치하라고 알려주지만, 스크립트 실행 후 `~/.bashrc`가 실행되지 않아서 발생한 문제였다.
```
source ~/.bashrc
```
그래도 되지 않는다면 오류 구문에서 설명한대로 설치해본다.
```
sudo apt install python-roslaunch
```