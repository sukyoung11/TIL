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

​		제공한 선택자와 일치하는 여러 element를 선택 - 문자열로 받음

​		node list 반환



`const h1 = document.querySelector('h1')`  # 태그 선택자

`const secondH2 = document.querySelector('#location-header')`  # id 선택자

태그는 중복 될 수 있으므로 id 선택자 사용



` query selector` 사용 이유 - id,class,tag 선택자 등을 모두 사용 가능하므로 더 구체적이고 유연하게 선택 가능



- live collection - 문서가 바뀔 때 실시간으로 업데이트 됨, 실시간 반영
- static collection - DOM이 변경되어도 collection 내용에는 영향을 주지 않음 `querySelectorAll()`



### DOM 변경

`document.createElement('li')` - 작성한 태그 명의 HTML요소를 생성하여 반환

`Element.append()` -특정 부모 노드의 자식 노드리스트 중 마지막 자식 다음에 노드 객체나 돔스트링 삽입, 반환값 없음

`Node.appendchild()` - 한 노드를 특정 부모 노드의 자식 노드 리스트 중 마지막 자식으로 삽입, 노드만 추가 가능, 한번에 오직 하나의 노드만 추가할 수 있음, 추가된 노드 객체를 반환

추가



`Node.innerText`  노드 객체와 그 자손의 텍스트 컨텐츠를 표현

`Element.innerHTML` 요소 내에 포함된 HTML마크업 반환



`ChildNode.remove()` 노드가 속한 트리에서 해당 노드를 제거

`Node.removeChild()` 돔에서 자식 노드를 제거하고 제거된 노드 반환



`Element.setAttribute(name,value)`  ('class','ssafy-location`)

`Element.getAttribute(attributeName)`



## Event

네트워크 활동이나 사용자의 상호작용 같은 사건의 발생을 알리기 위한 객체

이벤트 발생 - 마우스를 클릭하거나 키보드 누름, 특정 메서드를 호출 해 프로그래밍적으로 만들어 낼 수 있음

특정 이벤트가 발생하면 할 일을 등록한다

`EvevtTarget.addEventListrner(type,listener)`

type - 반응 할 이벤트 유형 ex) click

listener - 이벤트 발생 시 알림을 받는 객체,일, 동작(콜백 함수)

![image-20220427141245834](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20220427141245834.png)

- 이벤트 취소

`event.preventDefault()` - 현재 이벤트의 기본 동작 중단