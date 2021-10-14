# #1
```
$ systemctl start m
...
systemd[7470]: m.service: Failed to execute command: Exec format error
...
```
나의 경우 sh 파일을 service에 올렸는데, 위 오류로 인해 start가 안되는 상황이었다. 보통 셸 안에서는 sh 파일을 그냥 실행시키는 것이 가능하지만, 위의 상황에서는 sh라는 텍스트 타입 파일을 어떤 프로그램으로 실행시켜야 하는지 모른다.
```
#!/bin/bash
```
service에 올리려고 하는 sh 파일의 최상단에 위와 같이 실행할 프로그램을 명시해주어 해결했다.

# #2
```
E: Could not get lock /var/lib/dpkg/lock-frontend
E: Unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock-frontend),
is another process using it?
```
ubuntu 16.04에서 `apt install` 명령을 진행했을 때, 떴던 오류다. 느낌상 뜨는 원인 자체는 다른 프로세스에서 apt를 사용하고 있기 때문에 lock이 걸린 상태라서 접근이 제한 된 것 같은데, 아래와 같은 방법으로 이를 초기화해줄 수 있다.
```
sudo rm /var/lib/apt/lists/lock
sudo rm /var/cache/apt/archives/lock
sudo rm /var/lib/dpkg/lock*

sudo dpkg --configure -a
sudo apt update
```

# #3
```
After this operation, 79.7 MB of additional disk space will be used.
E: You don't have enough free space in /var/cache/apt/archives/.
```
갑자기 용량이 부족하다고 오류가 떠서 apt install을 할 수 없었다. 아카이브를 다음 명령으로 비워주면 된다.
```bash
$ sudo apt clean
```
