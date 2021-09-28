# #1
``` bash
$ ./configure --with-incompatible-bdb
checking build system type... x86_64-pc-linux-gnu
checking host system type... x86_64-pc-linux-gnu
checking for a BSD-compatible install... /usr/bin/install -c
checking whether build environment is sane... yes
checking for a race-free mkdir -p... /usr/bin/mkdir -p
checking for gawk... no
checking for mawk... mawk
checking whether make sets $(MAKE)... yes
checking whether make supports nested variables... yes
checking whether to enable maintainer-specific portions of Makefiles... yes
checking whether make supports nested variables... (cached) yes

...

checking for _mm_prefetch... yes
checking for strong getauxval support in the system headers... no
checking for weak getauxval support in the compiler... yes
checking for std::system... yes
checking for ::_wsystem... no
checking for Qt5Core Qt5Gui Qt5Network Qt5Widgets... no
configure: WARNING: Qt dependencies not found; bitcoin-qt frontend will not be built
checking whether to build Bitcoin Core GUI... no
checking for Berkeley DB C++ headers... no
configure: error: libdb_cxx headers missing, Bitcoin Core requires this library for wallet functionality (--disable-wallet to disable wallet functionality)
```
위와 같이 bitcoin core 설치를 위해 configure를 실행하는 과정에서 오류 발생.  
make 명령을 사용하려고 하니 configure이 정상적으로 끝나지 않았기 때문에 Makefile이 없다고 안됐었다.  
생각보다 바로 검색이 되지 않았는데 bitcoin core 레포에 있던 이슈에서 해결방법을 발견했다.  

https://github.com/bitcoin/bitcoin/issues/2998
``` bash
$ sudo apt-get install libdb++-dev
```