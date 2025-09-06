## basic program for parent and child process relation
```c
#include<stdio.h>
#include<unistd.h>
#include<stdlib.h>
/*
int main()
{
        int id;
        id=fork();
        if(id==0)
        {
                printf("child process\n");
        }
        else
        {
                printf("parent process\n");
        }
}*/
/*
int main()
{
        int id=fork();
        switch(id)
        {
                case 1:
                        printf("error");
                        break;
                case 0:
                        printf("child process\n");
                        break;
                default:
                        printf("parent process\n");
                        break;
        }
}*/
/*
int main()
{
        int id=fork();
        if(id==0)
        {
                sleep(5);
                printf("child process\n");
        }
        else
        {
                sleep(10);
                printf("parent process\n");
        }
}*/
/*
int main()
{
        int stat;
        int id=fork();
        if(id==0)
        {
                printf("child");
                exit(5);
        }
        id=wait(&stat);
        printf("%d",WEXITSTATUS(stat));
}*/
```
## 1.Explain the concept of process creation in operating systems.
```
A.process creation is while execution process will be created.
In process we can create multiple process based on our requirments.
Each process will have separate pid and the relation between those process will be parent child relation.
```
## 2.Differentiate between the fork() and exec() system calls.
```
fork():
by using fork() we can create a child process for parent process.
exec():
By using exec()  will useful to replace the process image with new program or new memory.
```
## 3.Write a C program to demonstrate the use of fork() system call. 
```c
#include<stdio.h>
#include<unistd.h>
#include<stdlib.h>
int main()
{
        int id;
        id=fork();
        if(id==0)
        {
                printf("child process\n");
        }
        else
        {
                printf("parent process\n");
        }
}
```
## 4.What is the purpose of the wait() system call in process management?
```
wait () system call is a blocking call  this wait system call will wait for the child process termination and exit status 
in process management.
```
## 5.Describe the role of the exec() family of functions in process management.
```
exec() family are 5 things
1.execl()
2.execv()
3.execlp()
4.execvp()
5.execve()
With this exec families will used to replace the new process image with new program
and in child process if we perform exec() function it will execute from the new process.
```
## 6.Write a C program to illustrate the use of the execvp() function.
```c
#include<stdio.h>
#include<stdlib.h>
#include<unistd.h>
#include<sys/wait.h>
int main()
{
        int status;
        char *args[4];
        args[0]="ls";
        args[1]=NULL;
        int pid=fork();
        if(pid==0)
        {
                execvp("ls",args);
                exit(5);
        }
        else
        {
                printf("parent process");
        }
        wait(&status);
}
```
## 7.How does the vfork() system call differ from fork()? 
```
fork() is a system call which will copy parent process to child process with separate memory space or physical frame in memory.
vfork() is a system call  which will share the parent memory space or physical frame in memory with child until exec() or exit ()call happen.
```
## 8.Discuss the significance of the getpid() and getppid() system calls.
```
getpid() is used to return the child process pid
getppid() is used to return the child's parent process pid .
```
## 9
## 10.Write a program in C to create a child process using fork() and print its PID. 
```c
#include<stdio.h>
#include<unistd.h>
int main()
{
        int id=fork();
        if(id==0)
        {
                printf("child process=%d\n",getpid());
        }
        else
        {
                printf("parent process=%d\n",getpid());
        }
}
```
## 11.Describe the process hierarchy in UNIX-like operating systems. 
```
process will set in execution.
Every first process called parent process will have ppid is init_->1.
In these we can have multiple process parent and child process we can create 1 or more child process.
Orphan process is the process that its parent  process will executed before child process and its ppid will be init_ called orphan process.
zombie process is the process that child process will executed and parent process will not collect the status from child using wait() system call
call zombie process.
```
## 12.Describe the process hierarchy in UNIX-like operating systems.
```
the purpose of exit() system call is to terminate the particular child process and
send its status to the parent process.
```
## 13.Discuss the role of the fork() system call in implementing multitasking.
```
fork() system call used to create new process of duplicate of its parent process
we can create mutliple child process and we can do mutliple tasks assign to the particular child process
```
## 14. Write a C program to create multiple child processes using fork() and display their PIDs.
```c
#include<stdio.h>
#include<unistd.h>
#include<sys/wait.h>
#include<stdlib.h>
int main()
{
        int status;
        int pid1=fork();
        if(pid1==0)
        {
                printf("%d child process pid\n",getpid());
                exit(0);
        }
        int pid2=fork();
        if(pid2==0)
        {
                printf("%d child process pid\n",getpid());
                exit(0);
        }
        waitpid(pid1,&status,0);
        waitpid(pid2,&status,0);
}
```
## 15.How does the exec() system call replace the current process image with a new one?
```
exec() system call will replace the current process with new program.
if we do in child process that current process imaage run untitl it meets exec call
when exec call meets it will perform command line arguments of perticular location it will moved
example: my file name is a.out and exec has ls -l command
if i call exec in the program it will replace the ls -l memory space with a.out
and it will perform the ls -l it will not perform the a.out.
```
