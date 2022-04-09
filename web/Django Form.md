# Django Form

사용자가 입력한 데이터에 대한 유효성 검증 작업을 쉽게 해줌 - 유효성 검사 도구

외부의 악의적 공격 및 데이터 손상에 중요한 방어 수단

유효성 검사 단순화, 자동화, 더 안전하고 빠르게

-  렌더링을 위한 데이터 준비 재구성
- 데이터에 대한 html form 생성
- 클라이언트로 부터 받은 데이터 수신 및 처리



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