# #1
```
No matching distribution found for django==2.2
```
코드잇 질문에 답변했던 오류. 질문자는 django를 설치하려고 했고, 2.2라는 특정버전을 사용하려고 했으나, pip가 가지고있는 리스트중에는 해당 버전이 없어서 발생하는 문제. pip를 업데이트하거나 버전을 확인해보아야 해결할 수 있음.

# #2
```
Traceback (most recent call last):
  File "main.py", line 14, in <module>
    if numbers[i] %2 == 1:
TypeError: unsupported operand type(s) for %: 'list' and 'int'
```
코드잇 질문에 답변했던 오류. list를 나머지 연산하면서 발생하는 오류.

# #3
```
PEP 8: E302 expected 2 blank lines, found1
PEP 8: E305 expected 2 blank lines after class of function definition, found 0
```
코드잇 질문에 답했던 오류. 파이참에서 개발자에게 주의로 자주 표시되는 경고인데, PEP8(https://www.python.org/dev/peps/pep-0008/) 이라고 하는 파이썬 개발 가이드라인과 맞지 않아서 발생한다. 여기에 맞춰주지 않아도 실행에는 문제가 없으나 가능하면 맞추어주기를 권장한다.

그럼에도 해제를 원한다면 [file]-[settings]에 [editor]-[inspections]에서 경고를 해제할 수 있다.

# #4
```
IndentationError: unexpected indent
```
코드잇 질문에 답했던 오류. 나도 여러 편집기를 왔다갔다 개발하면서 자주 겪었던 에러인데, 들여쓰기가 맞지 않아서 발생하는 오류. 혹시나 스페이스와 탭이 혼용되지 않았는지, 들여쓰기가 잘 되어있는지 확인해야한다.

