# Process

실행중인 프로그램의 인스턴스 (동적) - 상태를 가짐

프로그램 - 컴퓨터 파일에 저장된 실행 가능한 실행 파일 ( 정적)

멀티프로그램 시스템에 의해 각각의 프로세스는 독립적임



## life & scope

프로그램이 메모리 공간을 차지하고 있으면 live

scope - 변수들의 acess 할 수 있는 프로그램 영역 (local, global)



## local variables

함수 안에 정의된 변수

함수가 끝나면 해당 변수에 대한 공간 사라짐

## Global variables

함수 외부에 정의된 변수

static한 공간 차지

프로그램 시작부터 끝까지 live

## Static variables

파일 내부에서 정의된 변수 - 파일 안에서만 사용 가능

static한 공간 차지



## Context switching

프로그램 실행 중에 다른 프로그램을 실행할 경우 기존 프로그램의 진행 state(context)의 를 save 해야 함

프로그램을 다시 시작할 때는 state 복구

어떤 프로그램을 선택할지 scheduling





