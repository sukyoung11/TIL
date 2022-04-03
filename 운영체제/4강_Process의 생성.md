## operation on processes

1. fork() system call - 프로세스 생성

2. child process - parents process 의 주소 공간 복사

3. fork() 했을 때 return 값이 0 이면 child process, 0이 아니면 (실제로 부여된 pid) 면 parents

   

```c
#include <stdio.h>
#include <unistd.h>
int main()
{
	pid_t pid;
	pid = fork();
	printf("Hello, Process!\n");
}
```

```c
Hello, Process! // parents process
Hello, Process! // child process
```



```c
#include <stdio.h>
#include <unistd.h>
#include <wait.h>
int main()
{
	pid_t pid;
	pid = fork();
	if (pid > 0)
		wait(NULL); // parents process
	printf("Hello, Process! %d\n", pid);
}

```

```c
Hello, Process!,0 // child process
Hello, Process!,4214 // parents process
```



```c
int value = 5;

int main() 
{
	pid_t pid;
	pid = fork();

	if(pid ==0){ // child process
		value += 15;
		return 0;
	}
	else if (pid >0) { // parent process
		wait(NULL);
		printf( "Parent: value = %d\n", value); // LINE A
	}
}

```

```
Parent: value = 5
```

child 에서 바뀌는건 parents 에 영향을 주지 않음



```c
#include<stdio.h>
#include<unistd.h>
#include<wait.h>
/** How many processes are created?*/
int main() 
{
	fork(); // fork a child process
	fork(); // fork another child process
	fork(); // and fork another
    
`	return0;
}
// 총 8개의 프로세스 생성
```



```c
int main() 
{
	pid_t pid;
	pid = fork();
	
	if (pid == 0) { // child process
		execlp("/bin/ls","ls", NULL); // 새로운 프로세스로 갈아 끼움
		printf("LINE J\n");
	}
	else if (pid > 0) { // parent process
		wait(NULL);
		printf("Child Complete\n");
	}
	return0;
}

```

child process를 ls 로 갈아 끼웠기 때문에 기존 프로세스인 line j는 출력되지 않음



```c
int main() 
{
	pid_t pid, pid1;
	pid = fork();
	if (pid == 0) { // child process
		pid1 = getpid(); // pid1은 child pid
		printf("child: pid = %d\n", pid); // C
		printf("child: pid1 = %d\n", pid1); // D
	}
	else if(pid > 0) { // parent process
		pid1 = getpid(); // pid1은 parents pid
		printf("parents: pid = %d\n", pid); // A
		printf("parents: pid1 = %d\n", pid1); // B
		wait(NULL);
	}
	return 0;
}

```

```
parents: pid = 5157 (child pid) - A
parents: pid1 = 5156 (parents pid) - B
child: pid = 0    - C
child: pid1 = 5157 (parents pid) - D
```





```c
#define SIZE 5

int nums[SIZE] = {0, 1, 2, 3, 4};

int main() {
	pid_t pid;
	int i;
	
	pid = fork();
	
	if (pid == 0) { // child process
		for (i = 0; i < SIZE; i++) {
		nums[i] *= i;
		printf("CHILD: %d \n", nums[i]); // LINE X
        }
	}
	else if (pid > 0) { // parent process
		wait(NULL);
		for (i = 0; i < SIZE; i++) {
		printf("PARENT: %d \n", nums[i]); // LINE X
		}
	}
    return 0
}

```

```
0 1 4 9 16
1 2 3 4 5
```

