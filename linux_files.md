## program to read the info from the file by character by character.
```c
#include<string.h>
#include<stdio.h>
#include<unistd.h>
#include<fcntl.h>
int main()
{
        int fd=open("create1.c",O_RDONLY,0644);
        int ch;
        ssize_t n;
        while(n=read(fd,&ch,1)>0)
        {
                write(1,&ch,1);
                sleep(1);
        }

        close(fd);
}
```
