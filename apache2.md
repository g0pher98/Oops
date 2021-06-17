# #1
```
# service apache2 restart
* Restarting Apache httpd web server apache2
  ... AH01574: module proxy_module is already loaded, skipping
  ... AH01574: module proxy_http_module is already loaded, skipping
                            [ OK ]
```
모듈이 중복으로 올라가서 발생하는 경고문. 나의 경우 `a2enmod`로 이미 모듈을 올려준 상태에서 conf 파일에서 한번 더 로드하면서 발생했다. conf 파일에서 해당 load 부분을 지워주었더니 해결되었다.


# #2
```
# service apache2 restart
* Restarting Apache httpd web server apache2
  AH00558: apache2: Could not reliably determine the server's fully qualified domain name, ...
                            [ OK ]
```
`ServerName`이 지정되지 않은 설정이 있어서 뜨는 오류. 설정파일에 전역으로 `ServerName`을 추가해주면 해결.


# #3
```
# tail /var/log/apache2/error.log

...

... AH00957: HTTP: attempt to connect to 127.0.0.1:10001 (localhost) failed
```
서버에서 자꾸 503오류를 뱉어서 로그를 확인해보니 위와 같은 문제가 있었다. Port가 열려있지 않아서 발생하는 문제. `/etc/apache2/ports.conf`에서 해당 포트를 추가해주면 해결.