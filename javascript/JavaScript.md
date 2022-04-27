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

함수스코프

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



## 함수

함수를 정의하는 방법

1. 함수 선언식

2. 함수 표현식

자바 스크립트의 함수는 일급 객체

**일급객체**

1. 변수에 할당 가능

2. 함수의 매개변수로 전달 가능

3. 함수의 반환 값으로 사용 가능

매개 변수와 인자의 개수 불일치 허용 (인자 개수 적으면 undefined반환)

### 함수 선언식

함수의 이름과 함께 정의

호이스팅 가능 ( 함수 정의 전에 호출하기)

```javascript
function 함수의 이름(매개변수){
    몸통
}

function add(num1,num2) {
    return num1 + num2
}
add(1,2)

```

### 함수 표현식

함수를 표현식 내에서 정의하는 방식

함수의 이름을 생략하고 익명 함수로 정의 가능

호이스팅 불가능

```javascript
const add = function (num1,num2) {
    return num1+num2
}
add(1,2)
```

### rest parameter(...)

함수가 정해지지 않은 수의 매개변수를 배열로 받음 (python의 *args)

rest parameter로 처리한 매개변수에 인자가 넘어오지 않을 경우 빈 배열로 처리

### spread operator(...)

배열 인자를 전개하여 전달 가능

``` javascript
const spread = function(x,y,z){
    return x+y+z
}
const numbers = [1,2,3]
spread(...numbers) // 6
```



## Arrow Function

함수를 간결하게 정의하는 문법

fuction 키워드 생략 가능

매개변수가 하나면 ( ) 생략 가능

몸통의 표현식이 하나라면 { }, return 생략 가능

```javascript
const arrow1 = function(name){
    return `hello, ${name}`
}
const arrow1 = name => `hello,${name}`
```



## 문자열

### includes

```string.includes(value)```

문자열에 value가 존재하는지 판별 후, true/false 반환

### split

`string.split(value)`

```javascript
const str = 'a cat'
str.split() // ['a cat']
str.split('') //['a',' ','c','a','t']
str.split(' ') // 해당 문자열로 나눈 나머지 반환 ['a','cat']
```

### replace

```javascript
str.replace(' ','-') # 1개만 교체
str.replaceAll(' ','-') # 모두 교체
```

### trim

```javascript
srting.trim() // 문자열 시작과 끝의 모든 공백문자 제거
string.trimStart() // 문자열 시작의 공백문자 제거
str.trimEnd() // 문자열 끝의 공백문자 제거
```



## 배열

배열의 길이는 `array.length`

### reverse

```javascript
array.reverse()
```

### push & pop

``` javascript
array.push(100) // 배열의 가장 뒤에 요소 추가
array.pop() // 배열의 마지막 요소 제거
```

### unshift & shift

```javascript
array.unshift(100) // 배열의 가장 앞에 요소 추가
array.shift() // 배열의 첫번째 요소 제거
```

### includes

`array.includes(value)`

배열에 value가 존재하는지 판별 후, true/false 반환

### index0f

`array.index0f(value)`

배열에 특정 값이 존재하는지 확인 후 가장 첫번째로 찾은 요소의 인덱스 반환

없으면 -1반환

### join

`array.join([separator])`

separator는 선택적으로 지정, 생략 시 쉼표가 기본값

### spread operator

배열 내부에서 배열 전개 가능

얕은 복사에 활용 가능

```javascript
const array = [1,2,3]
const newArray = [0,...array,4]
console.log(newArray) // [0,1,2,3,4]
```



여기서 부터는 인자로 callback함수를 받음

callback함수 - 어떤 함수의 내부에서 실행 될 목적으로 인자를 넘겨받는 함수

### forEach

배열의 각 요소에 콜백 함수를 한번 씩 실행

```javascript
array.forEach(배열의 요소,[배열 요소의 인덱스,배열 자체])
const fruits = ['딸기','수박','참외']

fruits.forEach((fruit,index) => {
    console.log(fruit,index)
})
```

### map

배열의 각 요소에 콜백 함수를 한번 씩 실행 

반환 값을 요소로 하는 새로운 배열 반환

```javascript
const numbers = [1,2,3]

const newnumbers = numbers.map((num)=>{return num*2})
console.log(newnumbers)
```

### filter

return 값이 참인 요소들을 모아 새로운 배열 반환

```
const oddnums = numbers.filter((num,index)=> {return num%2})
```

### reduce

배열의 각 요소에 대해 callback함수를 한번 씩 실행

콜백 함수의 반환값을 하나의 값(acc)에 누적 후 반환

주요 매개 변수

- acc - 값이 누적되는 변수
- initialValue - 최조 콜백 함수 호출 시 acc에 할당되는 값, defalt는 배열의 첫번째 값

```javascript
const number = [1,2,3]
const result = numbers.reduce((acc,num)=>{return acc+num},0)
console.log(result) // 6
```

### find

배열의 각 요소에 대해 콜백 함수를 한번 씩 실행

콜백 함수의 반환 값이 참이면 조건을 만족하는 첫번째 요소 반환

찾는 값이 배열에 없으면  undefined반환

```javascript
const avengers = [{name: 'tony', age:45},
                 {name: 'tom', age:50}]
const result = avengers.find((avenger) => {
    return avenger.name === 'tony'
})
console.log(result) // {name: 'tony', age:45}
```

### some & every

some - 배열 중 하나라도 주어진 판별 함수를 통과하면 참을 반환

every - 배열의 모든 요소가 주어진 판별 함수를 통과할 경우 참을 반환
