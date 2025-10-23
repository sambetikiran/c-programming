## 1. What is meant by an IPC Mechanism?
```
Inter-Process Communication (IPC) mechanism is a method that allows different processes to exchange data and information with each other, either within the same system or across a network.
```
## 2. Why we use IPC Mechanism?
```
IPC is used to enable communication and data sharing between processes, synchronize their execution, and coordinate tasks to achieve parallel processing or modular program design.
```
## 3. What are the types of IPC Mechanisms?
```
The main types of IPC mechanisms are:
* Pipes
* named pipes
* Message Queues
* Shared Memory
* Semaphore
```
## 4. What is meant by “unicast” and “multicast” IPC?
```
Unicast IPC: Communication occurs between a single sender and a single receiver process.
Multicast IPC: Communication occurs between one sender and multiple receiver processes simultaneously.
```
5. What is meant by PIPES?
```
Pipes are a unidirectional IPC mechanism that allows one process to send data to another in a sequential stream, typically between a parent and child process.
```
6. What is meant by Blocking Calls?
```
A blocking call is an operation that makes a process wait until the requested operation (like reading or writing data) completes before continuing execution.
```
## 7. What are the types of Blocking Calls?
```
The main types are:
Blocking I/O: Process waits until operation completes.
Non-blocking I/O: Process continues execution even if the operation isn’t complete.
```
## 8. What are the different types of I/O Calls?
```
The main I/O call types are:
Blocking I/O
Non-blocking I/O
Asynchronous I/O
Synchronous I/O
```
## 9. What are the I/O calls we are used in IPC Mechanisms?
```
In IPC, the common I/O system calls used are:
* `read()`
* `write()`
* `open()`
* `close()`
* `pipe()`
* `mkfifo()`
```
## 10. What are the Blocking Calls used in IPC?
```
The blocking calls used in IPC are mainly:
* `read()` — waits until data is available.
* `write()` — waits until the data is written to the pipe or queue.
```
## 41. Implement a program that uses pipes for communication between a parent and child process. Show how data can be passed between processes using pipes.
```c
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
#include<unistd.h>
int main()
{
        int fd[2];
        int pid;
        char str[100];
        char buf[100];
        pipe(fd);
        printf("enter the input");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        pid=fork();
        if(pid<0)
        {
                perror("empty\n");
                exit(1);
        }
        if(pid==0)
        {
                close(fd[1]);
                printf("child is reading msg\n");
                sleep(2);
                int ret=read(fd[0],buf,sizeof(buf));
                printf("%s\n",buf);
                buf[ret]='\0';
                close(fd[0]);
        }
        else
        {
                close(fd[0]);
                int ret=write(fd[1],str,strlen(str)+1);
                close(fd[1]);
        }
}
```
## 43. Implement a program that uses Named pipes for communication between two processes. 
```c
// write process
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
#include<unistd.h>
#include<fcntl.h>
#include<sys/stat.h>
int main()
{
        mkfifo("myfifo",0666);
        char str[100];
        printf("enter the input\n");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        int fd=open("myfifo",O_WRONLY);
        printf("write process\n");
        write(fd,str,strlen(str)+1);
        close(fd);
}
// read process
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
#include<unistd.h>
#include<fcntl.h>
#include<sys/stat.h>
int main()
{
        char buf[100];
        mkfifo("myfifo",0666);
        int fd=open("myfifo",O_RDONLY);
        printf("read process\n");
        read(fd,buf,sizeof(buf));
        printf("%s\n",buf);
}
```
## 44. Write a C program to create a message queue using the msgget system call. Ensure that the program checks for errors during the creation process. 
```c
#include<stdio.h>
#include<sys/ipc.h>
#include<sys/msg.h>
#include<stdlib.h>
# define KEY 1220
int main()
{
        int msgid=msgget(KEY,0666|IPC_CREAT);
        if(msgid<0)
        {
                perror("msgget failed");
                exit(1);
        }
        printf("msg queue object is generated\n");
}
```
## 4545. Develop two separate C programs, one for sending messages and the other for receiving messages through a created message queue. 
```c
//unidirectional sending info
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
#include<sys/msg.h>
#include<sys/ipc.h>
#include<unistd.h>
#define KEY 1220
#define MSG_TYPE 1
int main()
{
        char rxbuf[100];
        char txuf[100];
        int msgid=msgget(KEY,0666|IPC_CREAT);
        long *ptr=(long*)txbuf;
        ptr[0]=MSG_TYPE;
        ptr[1]=getpid();
        printf("sending the msg");
        scanf("%s",txbuf+16);
        msgsnd(msgid,txbuf,8+strlen(txbuf+16),0);
}
//unidirectional reciving info
#include<stdio.h>
#include<stdlib.h>
#include<sys/msg.h>
#include<sys/ipc.h>
#include<string.h>
#define KEY 1220
#define MSG_TYPE 1
int main()
{
        int msgid=msgget(KEY,0666);
        char txbuf[100];
        printf("client is connected");
        msgrcv(msgid,txbuf,sizeof(txbuf),MSG_TYPE,0);
        printf("recived msg is %s \n",txbuf+16);
}
```
