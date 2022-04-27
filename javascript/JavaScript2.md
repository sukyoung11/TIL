# DOM 조작과 Event

## DOM 이란?

문서 프로그래밍 인터페이스

문서를 구조화하소 구조화된 구성 요소를 하나의 객체로 취급하여 다루는 논리적 트리 모델



## DOM 조작

Document는 문서 한 장에 해당하고 이를 조작

DOM 조작 순서 - 1. 선택 2.변경



### DOM 선택

- `document.querySelector(selector)`

  제공한 선택자와 일치하는 element 하나 선택

  첫번째 element를 반환

- `document.querySelectorAll(selector)`

​		제공한 선택자와 일치하는 여러 element를 선택

​		node list 반환



`const h1 = document.querySelector('h1')`  # 태그 선택자

`const secondH2 = document.querySelector('#location-header')`  # id 선택자

태그는 중복 될 수 있으므로 id 선택자 사용



### DOM 변경

`document.createElement('li')`





## Event

네트워크 활동이나 사용자의 상호작용 같은 사건의 발생을 알리기 위한 객체

이벤트 발생 - 마우스를 클릭하거나 키보드 누름, 특정 메서드를 호출 해 프로그래밍적으로 만들어 낼 수 있음

특정 이벤트가 발생하면 할 일을 등록한다

`EvevtTarget.addEventListrner(type,listener)`

type - 반응 할 이벤트 유형

listener - 일, 동작(함수)

![image-20220427141245834](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20220427141245834.png)