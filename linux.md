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
Each process will have separate pid and the relation beteween those process will be parent child relation.


