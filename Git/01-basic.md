# git 기초



## git이란?

What? 버전관리시스템

Why? 백업, 복구, 협업

--> 버전의 변경 사항을 기록한다.



## 기호/문법

~=home directory (user 계정명 파일)

. = 내 현재 위치

.. =위로(이전 경로)

touch = 파일 생성

```
$touch 계좌번호.py 잔액.py 송금.py 보안.py # 파이썬 파일 3개 생성
```

mkdir = 폴더 생성

```
$ mkdir homepage/ # homepage라는 폴더 생성
```



## 저장소 초기화

폴더->리포로 바꾸기

```
$ git init #(master)로 바뀌며 git이 관리한다는 뜻
```

리포->폴더

```
$ rm -rf .git/
```



## Commit하기

분장실 - 스테이지 - 메모리카드(쵤영)

분장실에서 파일을 수정함 (변경사항이 생김)

### 스테이지 올리기(staging)

분장실에서 스테이지로 올려야지 촬영을 할 수 있음

```visual basic
$git add <file name> # 파일 (변경사항) 올리기
$git add . # 현재 위치에 있는 모든 파일 (변경사항) 올리기
```

### Commit

촬영하기

```
$git commit -m 'message(변경 사항 메세지)' #촬영
```

```
$git log #commit결과 확인(촬영 결과 확인)
$git status #현재 상황 확인
```

**[정리] 커밋하기 위해서는 저장 --> add --> commit -m 의 과정을 거치면 된다**



## git hub에 백업하기

커밋하기 & 로컬에 리포 만들기 --> 둘을 연결하기--> 올리기

 ### 연결하기

백업할 장소를 지정하기 (단순히 가리키는 것)

```
$ git remote add origin http://git-hub.com ~~ # 깃허브 홈페이지에 나와있는 주소(링크) 연결
$ git remote -v # 연결 된 주소 확인
```

### 올리기(백업)

```
$ git push origin master # 깃허브에 올리기
```

## readme / .gitignore



## git hub에서 컴퓨터로 불러오기

### git hub에서 리포 복제해오기

맨 처음 한 번 실행

```
$ git clone 주소 # 리포->코드 클릭했을 때 나오는 clone 주소
```

### git hub의 내용 받아오기

```
$ git pull origin master
```







