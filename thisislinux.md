# 이것이 우분투 리눅스다 정리

## CH.4 서버를 구축할 때 알아야 할 필수 개념과 명령어

* Tap : 예상단어가 한개만 있을때는 한번만 눌러도 되지만, 여러개가 있는경우 두번 눌러서 후보군을 보여준다.

* /etc/skel : 처음 유저가만들어 질때 유저의 디렉토리에 기본으로 생성되는 파일들이 모여있는 곳


-----

#### 파일 유형
파일의 종류는 d,-,b,c,l 5가지 경우 등이 있다.

* d : 디렉토리, 폴더
* - : 일반 파일
* b : block Dvice를 의미하며 하드디스크, 플로피 디스크, CD/DVD 등의 저장장치
* c : Character Device, 마우스 키보드 프린터 등의 입출력 장비
* l : Link, 윈도우의 바로가기 아이콘과 같이 연결되어 있는 파일
