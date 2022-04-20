# Rest API

## HTTP

웹 상에서 컨텐츠를 전송하기 위한 약속

HTML 문서와 같은 리소스들을 가져올 수 있도록 하는 프로토콜(규칙)

웹에서 이루어지는 모든 데이터 교환의 기초( 요청/응답)

HTTP 2가지 특징 - stateless, connectionless (상태유지X,비연결성)

--> 쿠키와 세션을 통해 서버 상태를 요청과 연결

### HTTP request methods

자원에 대한 행위(수행하고자 하는 동작)정의

주어진 리소스에 수행하길 원하는 행동을 나타냄

GET(조회), POST(작성) ,PUT(수정),DELETE(삭제)

### HTTP response status codes

특정 HTTP 요청이 성공적으로 완료되었는지 여부를 나타냄

4xx -client error

5xx - server error

### URI

Uniform Resource Identifier

통합 자원 식별자

인터넷의 자원을 식별하는 유일한 주소

인터넷에서 자원을 식별하거나 이름을 지정하는데 사용되는 간단한 문자열



리소스 - HTTP요청의 대상(문서,사진 등 데이터)

각 리소스는 리소스 식별을 위해 HTTP전체에서 사용되는 URI로 식별 됨

하위 개념 - 

- URL - 자원 위치, 네트워크 상에서 자원이 어디 있는지 알려줌

- URN - 자원 이름, url과 달리 자원 위치에 영향을 받지 않음  ex) 국제 표준 도서 번호

  **--> 일반적으로는 URI를 URL과 같은 개념으로 보기도 함**

### URI의 구조

- Scheme (protocol) - 브라우저가 사용해야 하는 프로토콜 ex) https

- Host - 요청을 받는 웹 서버의 이름 ex) 구글 등

- Port - 웹 서버 상의 리소스에 접근하는데 사용되는 기술적인 문

  - http 표준 포트 - HTTP 80

- Path - 웹 서버 상의 리소스 경로  ex) patj/to/mylife.html

- Query(식별자) - 웹 서버에 제공되는 추가적인 매개 변수

  ​                             ? 뒤에 표시됨, &로 구분

- Fragment - 자원 안에서의 북마크의 한 종류, 특정 부분을 보여 줄 수 있도록 함

  ​                      #뒤에 표시 됨 - # 뒷 부분 요청이 서버에 보내지지는 않음



## RESTful API

### API

프로그래밍 언어가 제공하는 기능을 수행할 수 있게 만든 인터페이스

- 어플리케이션과 프로그래밍으로 소통하는 방법
- CLI는 명령줄, GUI는 그래픽, API는 프로그래밍을 통해 특정한 기능 수행

### web api

웹 애플리케이션 개발에서 다른 서비스에 요청을 보내고 응답을 받기 위해 정의된 명세

### REST

REpresentational State Transfer

API 서버를 개발하기 위한 일종한 소프트웨어 설계 방법론

네트워크 구조 원리의 모음

자원을 정의하는 방법에 대한 고민 

- REST의 자원과 주소의 지정 방법
  1. 자원(정보) - URI
  2. 행위 - HTTP method (GET,POST,PUT,DELETE)
  3. 표현 (자원과 행위를 통해 궁극적으로 표현되는 결과물)- JSON으로 표현된 데이터

### JSON

JavaScript objects notation

가벼운 데이터 통신 포맷

자바스크립트의 표기법을 따른 단순 문자열

사람들이 읽거나 쓰기 쉽고 기계가 파싱(해석,분석)하고 만들어내기 쉬움

파이썬의 dictionary, 자바스크립트 object 처럼 C계열의 언어가 갖고 있는 자료구조 - 쉽게 변화할 수 있는 **key - value 형태의 구조**를 갖고 있음



## Response

### Serialization

직렬화

데이터 구조나 객체 상태를 동일하거나 다른 컴퓨터 환경에 저장하고 나중에 재구성할 수 있는 포맷으로 변환하는 과정

Queryset, model instance 과 같은 복잡한 데이터를  JSON,XML 등 원하는 것으로 변환할 수 있게 중간 데이터 타입을 만들어줌 



### DRF

Django REST framework

장고의 폼/모델폼 클래스와 유사함

장고   drf

- response 

  django - HTML,  DRF -  JSON

- model  

  django - ModelForm, DRF - serializer



## Single Model

many = True (단일 객체가 아닐 때, 쿼리 등)
