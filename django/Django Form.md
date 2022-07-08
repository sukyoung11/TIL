# Django Form

사용자가 입력한 데이터에 대한 유효성 검증 작업을 쉽게 해줌 - 유효성 검사 도구

외부의 악의적 공격 및 데이터 손상에 중요한 방어 수단

유효성 검사 단순화, 자동화, 더 안전하고 빠르게

-  렌더링을 위한 데이터 준비 재구성
- 데이터에 대한 html form 생성
- 클라이언트로 부터 받은 데이터 수신 및 처리



### CSRF

사이트 간 요청 위조

웹 애플리케이션의 취약점 중 하나로 사용자가 자신의 의지와 무관하게 공격자가 의도한 행동을 하여 특정 웹페이지를 보안에 취약하게 하거나 수정, 삭제 등의 작업을 하게 만드는 공격 방법

이를 방어하기 위해 csrf token 사용

`{% csrf_token %}`

--> 사용자의 데이터에 임의의 난수값을 부여해 매 요청마다 해당 난수 값을 포함시켜 전송 시키도록 함

​	input type이 hidden으로 작성되며 value는 Django에서 생성한 hash 값으로 설정됨 

### input요소 표현 방법

1. from fields
2. widgets - fields 먼저 지정 후 필요시에 사용 



### model form을 쓰는 이유

모델 필드 속성에 맞는 HTML element를 만들어 줌

form의 내용을  DB에 저장



### 이미지 업로드

`ImageField()`

파일이 아닌 경로가 삽입 됨

pillow라이브러리 필요함



`FileField()` 의 상속을 받음

두개의 선택 인자 가짐

`image = models.ImageField(upload_to='images/',blank=True)



설치파일 그대로 설치할 때는

pip install -r requirements.txt



1. setting.py에 media_root, media_url 설정
2. uploadto에 media_root하위 경로 지정