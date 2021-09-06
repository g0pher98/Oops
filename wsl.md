# #1
WSL2 에서 `git clone` 시 `unable to access`가 뜨는 문제.  
`ping` 조차 동작하지 않음

https://github.com/microsoft/WSL/issues/4253  
WSL 공식 레포에 있던 이슈를 통해 해결. WIFI 드라이버를 업데이트한 후 재부팅하면 정상적으로 동작된다.