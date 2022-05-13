# AJAX

Asynchoronous JavaScript And XML 비동기식 자바스크립트

서버와 통신하기 위해 `XMLHttpRequest()`를 사용

JSON,XML(extended markup language),HTML 그리고 일반 텍스트 형식을 포함한 다양한 포맷을 주고 받을 수 있음 - 요즘은 JSON을 제일 많이 사용



## AJAX 특징

페이지 전체를 새로 고침 하지 않고서도 수행되는 **비동기성** 

​		->  전체 페이지가 아닌 일부분만을 업데이트

페이지 새로고침 없이 서버에 요청 가능

서버로 부터 데이터를 받고 작업을 수행할 수 있음



# Asynchronous JavaScript

** 동기식

순차적 직렬적 task 수행

요청을 보낸 후 응답을 받아야만 다음 동작이 이루어짐(blocking)

ex) 파이썬

## 비동기식

병렬적 task 수행

요청을 보낸 후 응답을 기다리지 않고 다음 동작이 이루어짐(non-blocking)

javascript는 single thread

ex) 자바스크립트



### 왜 비동기식을 사용하는가?

**사용자 경험**

동기식 코드라면 데이터를 모두 불러온 후 앱이 실행되기 때문에 그 때까지는 앱이 멈춘 것 처럼 보임

비동기식 코드는 데이터를 요청받고 응답 받는 동안 앱 실행을 함께 진행함

 -- > 데이터를 불러오는 동안 지속적으로 응답하는 화면을 보여줌으로써 더 쾌적한 사용자 경험을 제공



## call stack

요청이 들어올 때마다 해당 요청을 순차적으로 처리하는 stack형태의 자료 구조

함수가 들어감

## web api

 자바 스크립트 엔진이 아닌 브라우저 영역에서 제공하는 apl

`setTimeout()`,DOM events 그리고 AJAX로 데이터를 가져오는 시간이 소요되는 일을 담당

## Task queue

비동기 처리된 콜백 함수가 대기하는 queue형태의 자료구조

## Event Loop

콜스택이 비워있는지 확인한 후, task queu에 있는 콜백 함수를 콜스책에 넣어줌



## callback function

다른 함수에 인자로 전달된 함수

비동기 작업이 완료된 후 코드 실행을 계속하는데 주로 사용 - 비동기 콜백



# promise

동기식으로 처리해야하는 부분은 프라미스로 해준다.

## promise object

비동기 작업의 최종 완료 또는 실패를 나타내는 객체

## promise methods

이전 작업(promise)에 대한 미래의 완료 또는 실패와 그 결과값을 나타냄, 미래의 어떤 상황에 대한 약속

promise 반환

- 성공에 대한 약속(이행) `.then()`
- 실패에 대한 약속(거절)`.catch()`





# Axios

promise based HTTP client for the browser

브라우저를 위한 promise기반의 클라이언트

AJAX요청을 편리하게 하도록
