# 5. 프로세스간 통신

## Interprocess Communicarion

- independent processes

공유하는 데이터 x, 독립적

- cooperation processes

서로 영향을 주고 받음 , 데이터 공유**-->  IPC메커니즘 필요함**

### IPC ( Inter-process communication)

IPC의 두가지 모델

-  Shared memory -  공유 공간으로 통신
- message passing - 메세지 주고 받으며 통신, 운영체제한테 맡김

![image-20220416194105841](5강_Process간 통신.assets/image-20220416194105841.png)



## Shared Memory system

### Producer - Consumer Problem

생산자는 정보 생산, 소비자는 정보 소비

ex)

컴파일러(생산자)가 어셈블리 코드 생산, 어셈블러(소비자)는 코드를 가지고 기계어 생산

웹 서버(생산자)는 html 파일 생성,요청 보내면 브라우저(소비자)는 전송



생산자 프로세스 - 소비자 프로세스

생산자 프로세스와 소비자 프로세스는 동시에 실행 됨

**buffer** - 생산자 프로세스는 buffer 채우고, 소비자 프로세스는 비우고

buffer가 shared memory -> 생산자 프로세스와 소비자 프로세스가 공유하는 공간







생산자 프로세스는 buffer 채우고, in 증가 가득차있으면 대기

소비자 프로세스는 buffer 비우고, out증가

in하고 out이 같아질 때 까지 ( buffer가 빌 때 까지)

### shared memory 방식의 단점

프로세스가 많아질 경우 프로그래머가 직접 어쩌구

-> message-passing



## message passing system

### communication links

send, recieve

- direct
- indirect



- synchronous

- asynchronous



### direct communication

명시적으로 정해줌

send(P,message) - 누구한테 주는지 명시

recieve(Q,message)

한 링크만 성립

### indirect communication

메일박스로 통신 - **port**

send(A,message) -A는 메일박스(port )

recieve(A,message)

두개의 프로세스가 포트를 공유

두개의 프로세스 이상 공유 가능



블락킹(synchronous)이면 대기

논블락킹(asynchronous)은 대기 안하 

둘을 적절하게 사용
