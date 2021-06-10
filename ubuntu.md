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