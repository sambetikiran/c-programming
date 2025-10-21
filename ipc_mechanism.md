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
