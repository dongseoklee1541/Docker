# Linux
kernel과 command 을 합쳐놓은것(OS)이다. kernel 은 infra(하드웨어)를 관리하기 위해서, shell은 command를 관리하기 쉽게 하기 위해 만들어졌다.


### Kernel

infra 바로 위에서 관리하며 조종하는 녀석, 펌웨어와 비슷하다.

### shell

linux kernel 을 shell 이라는 껍질으로 둘러 쌓여있다. 이렇게 shell안에 있는 커널을 조작하고 제어한다. 일반적으로 리눅스 명령어를 사용 할때는
shell 위에서 하는것이다.

## Linux Shell Types

* sh(Bourne shell, 최상위 쉘) : By Unix shell, 기능은 적지만 최상이 부모이기 때문에 다른 쉘에서도 모두 사용 가능하다.

* bash (Bourne-agin shell) : Super shell in Linux, 가장 많이 쓴다.

* csh (C shell) : C like syntax , C와 비슷하지만 많이는 안쓰임

* tcsh (Enhanced-C shell): csh 강화버전

* ksh (korn shell)

* zch (Z shell) : shell의 끝판왕, 가장 강력하다


## Linux File System Directories / Filesystem Hierachy Standard

* **/bin** : 기본 명령어

* /boot : for booting , 부팅을 위한 명령어

* /dev : device file, cd-rom 디바이스 관련된 명령어

* **/etc** : config, passwrd, rc.d 기타 다양한 것들

* /home : user home dir , 실제 유저들이 존재하는 공간 그러나 root라는 superviser 는 /root 를 쓴다.

* **/lib** : shared library , 공유된 라이브러리 설치파일 같은것들

* /media : ssd , 외장하드 , 마운트에서 쓰는 것들

* opt : application software package , app 프로그램이라고 

* **/proc** : process info 

* /root : root home dir

* **/sbin** :  bin의 관리자용버전, ifconfig와 같은 것

* /srv : system data

* **/tmp** : temporary dir

* **/usr** : source or progams

* /user/local : 유저들이 사용하는 소스나 프로그램들을 말한다. 보통 mysql 같은 것을 설치할때 설치하는 공간

* **/var** : logs, ftp, spool, mail , log 파일과 같은 큰파일을 놓는 공간

* **/lost+found** : 사용이 더이상 안되는 파일들을 모아놓은 휴지통 같은 공간

* cf. **inode** : 파일 시스템을 메모리에 트리처럼 올려놓음, 파일을 찾기 쉽게 한다.

----

## linux Ports

숫자는 port번호이고 뒤는 명칭이다.

* **20 FTP(data)**
* **21 FTP(Control)**
* **22 SSH** : telnet의 보안 강화 버전
* **23 Telnet**

* **SMTP(Simple Mail Transfer) : Outgoing Mailserver 메일을 보내는 서버 
* 465 SMTPS

* 43 whois
* **53 DNS**
* **80 HTTP**
* **443 HTTPS**

* **110 POP3** : incoming Mailserver, 메일을 받는 서버
* 995 POP3S

## Command Line Tips

* $> tab → |  : 쓰고 싶은거 적당히 쓰고 탭하면 다써줌
* $> Arrow Up & Down : 화살표 위아래로 내리면 검색내역들 나옴
* $> ! : 검색한 히스토리에서 !v 를 하면 v로 시작되는 가장 최근의 기록을 보여줌
* $> !! : 방금 실행한 명령어를 다시 실행하고 싶을때
* $> Ctrl + A, Ctrl + E : 명령어를 막쓰다가 맨앞으로 가고 싶을때는 컨트롤 + a 맨 뒤로는 컨트롤 + e
* $> history
* $> man <명령> : <명령>에 대한 메뉴얼이 나옴

## 각종 명령어들

### root 명령어

* adduser <name> : 유저추가, 필요한 폴더 자동생성 cf. useradd : adduser와 기능은 같지만 폴더는 자동으로 생성 안해줌
  *  add user를 통해 자동생성된 디렉토리들 : bashrc,profile 등의 내용을 보고 싶다면 cat .profile 를 통해서 보자.
* passwd <account-name> : 유저의 패스워드를 다시 입력할 수 있음, 패스워드 까먹었을때 사용하면 좋겠쥬?
* deluser <account-name> : 유저를 삭제하는 것, 다만 디렉토리는 지워지지 않음 디렉토리는 데이터라고 생각하고 있기 때문이다.

* rmdir <dir> : 디렉토리를 삭제하는 키워드, 디렉토리가 비어있지 않으면 삭제가 되지 않는다.
* rm -rf <dir> : 디렉토리를 삭제하는 키워드, 디렉토리에 내용이 있어도 삭제됨, -rf 가 들어가면서 묻지말고 다 삭제하게 됨
* su - <account-name> : 해당 사용자로 접속


#### 기본 명령어
* ls : 파일 리스트 보기 
* touch <파일이름> : touch 는 파일을 생성하는 명령어이다.
* cat : 파일 내용 보기
----
* head -<n> : 내용을 볼때 위에서부터 n 만큼 보겠다. ex) head -10 : 위에서 10줄만 보여줘
 * tail -<n> : head와 반대로 밑에서부터 보겠다.
----
* pwd(present work directory) : 현재 디렉토리를 알려줘
* which : 해당 파일이 어느 폴더에 있니?
* clear : 화면 지우기
* echo : 파이썬의 print와 같은 역할. ex) echo $HOME
  * cf. echo "ttt" > test.txt : test.txt 에 ttt를 입력해라. 여기서 ">" 꺽쇠 하나는 새로 쓰는것, ">>" 는 attach, 뒤에 이어서 쓰는 것이다.
----
* cd : "cd .." 상위 디렉토리로 이동
  * cd - : 이전 상태로 돌아가기(history 에서 앞으로 돌아가는 것)
----
* mkdir : dir를 만든다
  * rmdir : dir를 지운다.
----
* cd <filename> <path>: 복사해서 이동시키기 덮어 씌우기는 안됨( 만약 덮어씌우고 싶다면, cd -af <filename> ... 으로 실행하자.)
 * mv <filename> <path> : 그대로 이동시키기
 * rm <filename> : 파일 삭제
* ll = alias에 의해 'ls -alf'의 별칭이다. cf. ls -alF :a가 붙었기에 모든걸(숨김 폴더도) 한줄씩 보여줘
* la = alias에 의해 'ls -A' : 한줄에 다 보여줘
* l = alias에 의해 'ls -CF' : 숨김폴더는 제외하고 보여줘


* (sudo) apt-get install/ <name> : apt 폴더에 라이브러리를 설치함
  * apt-get update : install 전에 apt-get 을 업데이트해 최신화 시켜주자. 파이썬에서 pip 업데이트 하듯이 말이다.
  * ex) apt-get install vim : vim을 설치해라.
 
 
----

* df : 디스크 사용량 확인
* du <dir>: 디렉토리의 사용용량을 알고 싶을때 사용, ex) du /home
  * du -sk(m) <dir> : 디렉토리 이하의 값들을 한번에 모두 더해서 보여달라.
----
* free (-m) : 메모리 사용량 확인 cf. swap은 디스크에서 빌려온 것들을 말한다.
* top : CPU 코어 점유율, 사용량 확인
* vmstat (n): 메모리와 CPU 등 사용량을 요약해서 한번에 보여줌 , n 을 넣을 경우 n초 단위로 갱신됨
----

* echo **'#!/bin/sh'** > tt.sh 
* chmod <nnn> : 읽기쓰기 권한을 바꾸는 것, 2진수로 이루어져 있으며 나(3bit) 그룹(3bit) 상대(3bit) 로 이루어져있다.
* chown <username>:<groupname> <filename> : 지정한 유저와 그룹으로 파일의 권한 변경