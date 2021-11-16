# #1
```
frida.InvalidArgumentError: gDBus.Error:re.frida.Error.InvalidArgument: Script(line 9): SyntaxError: invalid token
```
js의 백쿼터(`)를 사용해서 뜬 오류. 문법을 수정해주니 잘 동작한다.

# #2
```
TypeError: cannot read property 'readU8' of null
```
` Module.findExportByName` 메소드를 사용할 때, 없는 함수에 참조해서 null이 떴지만, `Interceptor.attach`메소드에 그대로 사용해버리면서 결론적으로 함수를 찾지 못해 발생하는 오류.