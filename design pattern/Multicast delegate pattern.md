# Multicast delegate pattern

## What

- delegate pattern의 변형으로 동작 패턴에 해당

- 기존 delegate의 one-to-one relationships 대신 one-to-many delegate relationships을 만들 수 있음



![image-20220609154535743](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20220609154535743.png)



**object needing a delegate** -> 하나 이상의 delegates를 갖고 있는 개체

**delegate protocol**  ->  대리자가 구현하거나 구현해야 하는 메서드 정의

**delegate** -> delegate protocol을 구현하는 개체

**multicast delegate** -> delegate 를 보유하고 delegate에 합당한 이벤트가 발생할 때마다 각 delegate에게 알려주는 helper class ( delegate pattern과의 차이점)



## Why?

one-to-many delegate relationships를 만들 수 있음

--> 다른 개체에 변경 사항이 발생할 때마다 여러 개체에 알릴 수 있으며 각 delegate는 자체 state를 업데이트하거나 응답으로 관련 작업을 수행함