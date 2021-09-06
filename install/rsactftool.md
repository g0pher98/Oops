# #1
```
# pip install -r requirements.txt

...
Building wheels for collected packages: gmpy, gmpy2
  Building wheel for gmpy (setup.py) ... error
  ERROR: Command errored out with exit status 1:

  Running setup.py clean for gmpy
  Building wheel for gmpy2 (setup.py) ... error
  ERROR: Command errored out with exit status 1:
```
gmpy2 설치오류가 발생. 아무리 검색해봐도 잘 안나옴.
```
sudo apt-get install libgmp-dev
```
이것저것 다 시도해보다가 가장 마지막에 성공한 것은 아래 링크임.

https://stackoverflow.com/questions/50474091/gmpy2-doesnt-install/50554366#50554366

```
sudo apt install libmpc-dev
sudo apt install python3-pip
pip3 install --user gmpy2==2.1.0a2
```