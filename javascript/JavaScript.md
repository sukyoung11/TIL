# JavaScript

장고는 서버 입장에서 사용자의 요청 분석 & 응답을 구현 

자바스크립트는 응답을 받아서 처리하는 브라우저를 다룸

- 브라우저 화면을 **동적**으로 만들기 위함

- 브라우저를 조작할 수 있는 **유일한 언어**

## Browser

브라우저가 할 수 있는 일

### DOM조작 

문서(HTML) 조작(문서를 프로그램으로 조작 가능)

**파싱** 

구문 분석,해석

브라우저가 문자열을 해석하여 돔 트리로 만드는 과정

### BOM조작 

브라우저 조작

브라우저의 창이나 프레임을 추상화해서 프로그래밍적으로 제어할 수 있도록 제공하는 수단

### JavaScript core (ECMA)

브라우저(BOM,DOM)을 조작하기 위한 명령어 약속 (언어)



## ECMA

ECMA Script는 ECMA에서 규격에 따라 정의한 언어



## 변수와 식별자

### 식별자 작성 스타일

식별자는 반드시 문자, $, _ 로 시작, 대소문자 구분

- 카멜 케아스(cameCase) - 변수,객체,함수에 사용
- 파스칼 케이스(PascalCase) - 클래스, 생성자에 사용
- 대문자 스네이크 케이스(SNAKE_CASE) - 상수(변경될 가능성 X)에 사용

### 변수 선언 키워드

선언 - 할당 - 초기화

#### `let`

 재할당 가능

```javascript
let number = 10 // 선언 & 초기값 할당
number = 10 // 재할당
console.log(number) // 10
```

재선언 불가능

```javascript
let number = 10
let number = 20 // 불가능
```



#### `const`

재할당 불가능( = ), 값을 바꾸는 건 가능(append 등)

```javascript
const number = 10  // 선언 & 초기값 할당
number = 10 // 재할당 불가능, 에러발생
```

재선언 불가능



#### 블록 스코프

if, for, 함수 등의 중괄호 내부를 가리킴

블록 스코프를 가지는 변수는 블록 바깥에서 접근 불가능 - `let`,`const`

```javascript
let x = 1
if(x===1){
    let x = 2
    console.log(x) // 2
}
console.log(x) // 1
```

#### `var`

현재는 사용하지 않음

var 로 선언한 변수는 재선언 재할당 모두 가능

```javascript
var number = 10
var number = 50
```

**호이스팅**

변수를 선언 이전에 참조할 수 있는 현상

```javascript
console.log(x)
var x = '10'  // 가능

console.log(x)
let x = 10  // 에러
console.log(x)
const x = 10  // 에러
```



## 데이터 타입

자바스크립트의 모든 값은 특정한 데이터 타입을 가짐

원시타입(primitive)과 참조타입(reference)으로 분류됨

### 원시타입

객체가 아닌 기본 타입

변수에 해당 타입의 값이 담김

다른 변수에 복사할 때 실제 값이 복사됨

- 숫자(number)

  정수/실수 구분 안함

  `NaN` 계산 불가능 한 경우 반환되는 값

- 문자열

​		텍스트 데이터를 나타냄

​		템플릿 리터럴 == 파이썬 f스트링  - 백틱(`)+${a}+백틱

- undefined

​		변수의 값이 없음을 나타내는 데이터 타입

​		변수 선언 이후 직접 값을 할당하지 않으면 자동으로 undefined가 할당 됨

- null

  변수의 값이 없음을 의도적으로 표현할 때 사용

  개발자가 의도적으로 필요한 경우 할당

- Boolean 

​		소문자로 표현

### 참조타입

객체 타입의 자료형

변수에 해당 객체의 참조 값이 담김

다른 변수에 복사 할 때 참조 값 복사



## 연산자

- 할당 연산자 `=` , `++` = `+=`

- 비교 연산자
- 동등비교연산자 `==`  - 사용하지 않음, 형을 알아서 변환해버려서...
- 일치비교연산자 `===`  - 우리가 아는 원래 아는 `==`  

- 논리 연산자- `&&` `||` `!`
  - 삼항 연산자 `(true ? 1 : 2)` - 왼쪽 조건식이 참이면 `:` 앞의 값, 아니면 뒤의 값





## 조건문

### `if`

```javascript
if (nation === 'korea'){
    console.log('안녕')
} else if (nation === 'france' ) {
    console.log('Bonjour')
} else {
    console.log('hello')
}
```



### `switch`

표현식의 결과값을 이용한 조건문

```javascript
switch(nation) {
    case 'korea' : {
        console.log('안녕')
        break
    }
    case 'france' : {
        console.log('Bonjour')
        break
    }
    defalt: {
        console.log('hello')
    }
}
```

`break` 가 없으면 참인 조건 밑의 구문들 모두 다 실행



## 반복문

### `while`

```javascript
while (i<6){
    console.log(i)
    i++ // i+=1
}
```



### `for`

`:` 으로 구분되는 세 부분으로 구성

```javascript
for (let i=0; i<10; i++){
    console.log(i)
}
```



### `for ... in`

주로 객체(자바스크립트에서 말하는 객체는 딕셔너리)의 속성 순회

```javascript
for (let capital in caritals) {
    console.log(capital) // key값 출력
}
```



### ` for ... of`

반복 가능한 객체 순회 - array, map

``` javascript
for (let fruit of fruits) {
    console.log(fruit)
} //파이썬에서의 for fruit in fruit:
```



