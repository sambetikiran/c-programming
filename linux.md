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
```
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
