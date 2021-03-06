# OOP 객체지향 프로그래밍

## 객체

**파이썬은 모두 객체로 이뤄져 있다.**

객체는 특성 타입의 instance(사례)이다.

객체는 메모리에 할당된 값

객체의 특징

- 타입 - 어떤 연산자와 조작이 가능한지

- 속성 - 어떤 데이터를 가지는지

- 조작법 (method) - 객체가 할 수 있는 행위

따라서 **객체는 데이터를 가지며 어떤 일(함수)을 할 수 있는 것**



의자는 관념(실존하지 않음) - 이데아가 담겨있을 뿐 --> class (공통된 특성들을 담아놓음)

나와 상호작용 하는 순간 실존함--> **`instance()`**

chair(class) /  a chair(instance)



## 객체지향 프로그래밍

프로그래밍을 여러개의 **독립된 객체(실존하는 존재)들과 그 객체들 간의 상호작용**으로 파악하는 프로그래밍

함수들(명령어들)이 목록으로 쭉 이어진게 아니라...(절차지향)

!= 절차지향 프로그래밍 - 데이터와 함수로 인한 변화

```python
a = [1,2,3]
a = sorted(a)
a = reversed(a)

# a 라고 하는 리스트가 계속 흘러다님
```

```python
a = [1, 2, 3]
a.sort()
a.reverse()
a.append(4)

# 객체 스스로가 데이터를 갖고 있고 계속 활용 가능
```

장점 - 코드의 직관성, 활용의 용이성, 변경의 유연성, 소프트웨어 개발과 보수가 간편해짐

 ex)  사각형의 넓이 구하기

​         사각형 - class

​         각각의 사각형 - instance

​         사각형의 정보 (가로 길이, 세로 길이) - attribute(속성)

​         사각형의 행동 (넓이 구하기) -method

​    

## OPP 기초

### 기본 문법

- 클래스 정의 `class MyClass:`

- 인스턴스 생성 `my_instance = MyClass()`
- 메소드 호출 `my_instance.my_method()` 함수
- 속성 `my_instance.my_attribute` =   객체들이 가지게 될 상태 / 데이터

 ### 객체 비교하기

- == 

  동등한, 변수가 참조하는 객체가 동등한 경우, 동일한 대상을 가리키고 있다는 뜻은 아님

- is

  동일한, 두 변수가 동일한 객체를 가리키는 경우



## 인스턴스

### 인스턴스 변수

인스턴스가 개인적으로 가지고 있는 속성

`self.name` 으로 정의

### 인스턴스 메소드

인스턴스 변수를 사용하거나 값을 설정하는 메소드

호출 시, 첫번째 인자로 `self` 가 전달됨

함수 내부에 인스턴스를 던져주도록 설계

메소드를 정의할 때 `self` 로 받도록

- self

  인스턴스 자기 자신

### - 생성자 메소드

인스턴트 객체가 생성될 때 자동으로 호출되는 메소드

인스턴스 변수를 정의하기 위해 사용

변수의 초기값을 설정할 때 사용

`__init__(    )`

### - 소멸자 메소드

`__del__`

### - 매직 메소드

`__`

`__str__` print()를 썼을 때 어떤 결과가 나올 지 지정, 프린트 함수 쓸 때 자동으로 호출

`__repr__` 기계가 읽을 수 있는 형태로 문자 출력

`__len__` 길이 지정

`__gt__` greater than - 대소비교 >

`__lt__` less than <

특정한 함수를 호출할 때 내부적으로 특정 메소드가 실행되도록



## class

### 클래스 변수

모든 인스턴스가 똑같이 갖고 있는 속성

```
class Circle:
	pi = 3.14
```

```
Circle.pi
3.14
```

### 클래스 메소드

 **클래스를 조작하고 싶을 때**

함수 내부에 클래스를 던져 주도록 설계

@데코레이터를 이용하여 정리

메소드를 정의할 때 `cls`로 받도록

``` python
class My class:
	
	@classmethod
	def class_method(cls):
	return cls
```

 ### 인스턴스와 클래스 간의 이름 공간

클래스를 정의하면 클래스와 해당하는 이름 공간 생성

인스턴스를 만들면 인스턴스 객체가 생성되고 이름 공간 생성

인스턴스에서 특정 속성에 접근하면 인스턴스 - 클래스 순으로 탐색

### 스태틱 메소드

해당 클래스가 사용할 메소드

@데코레이터를 사용하여 정의

인자를 아무것도 넘겨주지 않음

클래스나 인스턴스를 조작할 생각은 없는데 함수를 쓸거야ㅑ...



```python
# 인스턴스 메소드, 클래스 메소드, 스태틱 메소드 정리

class Myclass:
    
    def method(self):
        return 'instance method' , self
    
    @classmethod
    def classmethod(cls):
        return 'class method', cls
    
    @staticmethod
    def staticmethod():
        return 'static method'
```





## 객체 지향의 핵심 개념

### 추상화

현실세계를 프로그램 설계에 반영  ex) 사람들을 특성에 따라 분류

###  상속

두 클래스 사이 부모 자식 관계를 성립하는것

클래스는 상속이 가능함

하위 클래스는 상위 클래스에 정의된 속성, 행동, 관계 및 제약 조건을 모두 상속 받음 

상속을 통해 메소드를 재사용할 수 있음 (코드 재사용성 높아짐)

- `isinstance` 로 확인 가능

```python
class Person:
	pass
class Professor(Person):
	pass
class Student(Person):
	pass
	
p1 = Person()
prof1 = Professor()
s1 = Student()

isinstance(p1, Person) # True
isinstance(s1, Person) # True
isinstance(p1, Student) #False
```

- `issubclass(하위, 상위)` 

오른쪽이 왼쪽의 상위 클래스인지 여부

```python
issubclass(Student, Person) # True

issubclass(bool, int) # True
issubclass(float, int) # False
```

- `super()`  

자식클래스에서 부모 클래스를 사용하고 싶은 경우

부모클래스의 요소 호출 가능

- **메소드 오버라이딩**

자식클래스에서 재정의 가능

부모 클래스 talk( ) --> 안녕하세요 일때, 자식클래스 talk() --> 안녕! 으로 바꾸기 가능

- 다중 상속

  두개 이상의 클래스를 상속 받는 경우, 중복된 속성이나 메소드는 상속 순서에 의해 결정됨

- mro메소드   
- 인스턴스 --> 자식 클래스 --> 부모 클래스 순으로 탐색

### 다향성

동일한 메소드가 클래스에 따라 다르게 행동할 수 있음

즉, 서로 다른 클래스에 속해있는 객체들이 동일한 메세지에 대해 다른 방식으로 응답할 수 있움

**오버라이드** 

기존에 있던 걸 재정의, 덮어쓰기

### 캡슐화

객체의 일부 내용에 대해 외부로부터의 직접적인 엑세스를 차단

파이썬에서 암묵적으로 존재하지만, 언어적으로는 존재하지 않음

 ``` python
 class Person:
 	def get_name(self):
 		return self.name
 		
 	def set_name(self.name):
         self.name = name
 ```

``` 
p2 = Person()
p2.set_name()
```

접근제어자 종류

- public Acess Modifier - 어디서나
- Protected - 상속관계

​        언더바 1개로 시작, 암묵적 규칙에 의해 부모 클래스 내부와 자식 클래스에서만 호출 가능

​        하위클래스 오버라이드 허용

```python
class Person:
	def __init__(self, name, age):
        self.name = name
        self._age = age
		
	def get_age(self):
        return self._age
    
    
p1 = Person(김싸피, 30)
p1.get_age()  # 30 , protect method는 get_age 메소드를 활용하여 호출
       
```

- Private - 본인민

  언더바 2개로 시작

  본 클래스 내부에서만 사용 가능

  하위 상속, 호출 불가능

  외부 호출 불가능

  ```python
  class Person:
  	def __init__(self, name, age):
          self.name = name
          self.__age = age
  		
  	def get_age(self):
          return self.__age
      
      
  p1 = Person(김싸피, 30)
  p1.get_age()  # 30 , private method는 get_age 메소드를 활용하여 호출
  p1.__age #오류
  ```



- getter, setter 메소드

  getter 는  변수의 값을 읽는 메소드 - @property 데코레이터 사용

  setter는 변수의 값을 설정하는 메소드 @변수.setter사용

``` python
class Person:
    def __init__(self, age):
        self._age = age
     
    @Property
    def age(self):
        return self._age
    
    @age.setter
    def age(self, new age):
        return self.age = new age - 10

    
p1 = Person(10)

p1.age()  # 오류, @property - 메서드를 정의했는데 속성처럼 쓰도록 한다

p1.age() #setter가 있으면 값을 조작 가능
```





















