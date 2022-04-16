# 6강 Concurrency : Deadlock and starvation

## Deadlock

하나 이상의 프로세스가 서로 기다리고 있는 것

- reusable resource
- consumable resource

### 발생조건

- mutual exclusion
- hold and wait - 프로세스가 어떤 자원을 갖고 있으면서 또 다른 자원을 요청할 때
- no preemption - 자원을 강제로 뺏을 수 없을 때
- *circular wait -

Deadlock을 해결하려면 어떤 프로세스가 어떤 자원을 갖고 있고 어떤 자원을 요청하는지 알아야함

### 해결방법

- deadlock prevention - 예방, 보수적인 방법, 비효율적 
- deadlock avoidance - 중도
- deadlock detection - 취소하고 다시 시작