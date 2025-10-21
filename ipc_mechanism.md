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

