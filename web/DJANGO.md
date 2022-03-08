# DJANGO

## Web

### static web page (정적웹페이지)

모든 상황에서 모든 사용자에게 동일한 정보를 표시

### Dynamic web page (동적웹페이지)

추가적인 처리 과정 이후 클라이언트에게 응답을 보냄

방문자와 상호작용하기 때문에 페이지 내용은 그때그때 다름



## Web framework

웹 페이지를 개발하는 과정에서 어려움을 줄여주는 것

### MTV Pattern

model - templete - view

요청 -> URLS -> View -> 응답



## django intro

### project

여러 어플리케이션의 집합

- setting.py - 어플리케이션의 모든 설정을 포함
- urls.py - 사이트의 url과 적절한 views의 연결을 지정
- manage.py - 장고 프로젝트와 다양한 방법으로 상호작용하는 커맨드라인 유틸리티

### Application

앱은 실제 요청을 처리하고 페이지를 보여주고 하는 등의 역할을 담당

일반적으로 앱은 하나의 역할 및 기능 단위로 작성함

- models.py - 앱에서 사용하는 모델 정의
- admin.py - 관리자용 페이지 생성
- views.py - view 함수들이 정의 되는 곳

프로젝트에서 앱을 사용하기 위해서는 반드시 setting.py - INSTALLED_APPS 리스트에 추가해야함



## 요청과 응답

urls.py 파일에서 path('주소'/불러올 함수) - 요청을 보내고 응답을 받는 과정

view함수는 무조건 request가 필요함



## Template

장고에서 템플릿을 확인할 때 모든 앱의 템플릿을 하나로 모아서 확인함 - 따라서 다른 앱이라도 이름이 같은 템플릿을 추가하면 원하는 결과 안나올 수도 있음

따라서 templates/파일안에 앱과 같은 이름의 폴더 생성, 그 안에 html을 추가함



BASE_DIR 은 프로젝트의 root 폴더



url을 통해서 들어가면 무조건 GET 형태로 요청이 들어감

POST 형태로 요청을 보내려면 form method를 활용해야 함



{% %} 는 template tags 



## Model

### 데이터베이스

체계화 된 데이터의 모임

### 쿼리

데이터를 조회하기 위한 명령어

### 데이터 베이스 기본 구조

- 스키마 - 구조, 표현방법, 관계 정의
- 테이블
- PK(기본키)



## ORM

