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

- models.py - 앱에서 사용하는 모델 정의

- admin.py - 관리자용 페이지 생성

- views.py - view 함수들이 정의 되는 곳

  



## Template



