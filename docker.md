# #1
```
Invalid top-level property "service". Valid top-level sections for this Compose file are: version, services, networks, volumes, secrets, configs, and extensions starting with "x-".

You might be seeing this error because you're using the wrong Compose file version. Either specify a supported version (e.g "2.2" or "3.3") and place your service definitions under the `services` key, or omit the `version` key and place your service definitions at the root of the file to use version 1.
For more on the Compose file format versions, see https://docs.docker.com/compose/compose-file/
```
문법문제. 가장 첫문장을 잘 읽어보면 문제점을 알 수 있다. `Invalid top-level property "service".` 이 경우에는 services가 아닌 service로 기입했기 때문에 오류가 발생한 것.