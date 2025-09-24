## 1.program to print HELLO WORLD
```c
#include<stdio.h>
#include<string.h>
#include<pthread.h>
void*thread_fun(void *arg)
{
        printf("hello world\n");
}
int main()
{
        pthread_t tid;
        pthread_create(&tid,NULL,thread_fun,NULL);
        pthread_join(tid,NULL);
}
```
## 2.Create 5 threads, each printing its own thread ID.
```c
#include<stdio.h>
#include<pthread.h>
void * thread_fun(void *arg)
{
        static int i=1;
        printf("thread-%d ID is %lu\n",i,pthread_self());
        i++;
}
int main()
{
        pthread_t tid[5];
        for(int i=0;i<5;i++)
        {
                pthread_create(&tid[i],NULL,thread_fun,NULL);
                if(pthread_create==0)
                {
                        perror("error");
                }
        }
        for(int i=0;i<5;i++)
        {
                pthread_join(tid[i],NULL);
        }
}
```
## 3.Write a program where the main thread waits for a child thread using pthread_join().
```c
#include<stdio.h>
#include<pthread.h>
#include<unistd.h>
void *thread_fun(void *arg)
{
	printf("child thread is id=%lu\n",pthread_self());
	sleep(2);
}
int main()
{
	pthread_t tid;
	pthread_create(&tid,NULL,thread_fun,NULL);
	if(pthread_create==0)
	{
		perror("error");
	}
	pthread_join(tid,NULL);
	printf("main thread is id=%lu\n",pthread_self());
}
```
## 8.Write a C program to create a thread that prints the current date and time?
```c
#include<stdio.h>
#include<time.h>
#include<pthread.h>
struct datetime
{
        int day;
        int year;
        int month;
        int second;
        int hour;
        int minute;
};
void *thread_fun(void *arg)
{
        time_t now;
        struct tm *local;
        struct datetime dt;
        time(&now);
        local=localtime(&now);
        dt.day=local->tm_mday;
        dt.year=local->tm_year+1900;
        dt.month=local->tm_mon+1;
        dt.second=local->tm_sec;
        dt.hour=local->tm_hour-12;
        dt.minute=local->tm_min;
        printf("current date is--%d/%d/%d\n",dt.day,dt.month,dt.year);
        printf("current time is--%d:%d:%d\n",dt.hour,dt.minute,dt.second);
}
int main()
{
        pthread_t t1;
        pthread_create(&t1,NULL,thread_fun,NULL);
        pthread_join(t1,NULL);
}
```
## 7.Implement a C program to create a thread that calculates the square of a number? 
```c
#include<pthread.h>
void *square(void *arg)
{
        int a=10;
        int sq=a*a;
        printf("square is %d\n",sq);
}
int main()
{
        pthread_t sqr;
        pthread_create(&sqr,NULL,square,NULL);
        pthread_join(sqr,NULL);
}
```
## 10.Implement a C program to create a thread that checks if a given string is a palindrome?
```c
#include<stdio.h>
#include<pthread.h>
#include<string.h>
void *palind(void *arg)
{
        char *str=(char *)arg;
        int len=strlen(str);
        int flag=1;
        for(int i=0;i<len;i++)
        {
                if(str[i]!=str[len-i-1])
                {
                        flag=0;
                        break;
                }
        }
        if(flag)
        {
                printf("it is palindrome");
        }
        else
        {
                printf("it is not palindrome");
        }
}
int main()
{
        pthread_t pal;
        char str[100];
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        pthread_create(&pal,NULL,palind,&str);
        pthread_join(pal,NULL);
}
```
## 1.Write a C program to create a thread that prints "Hello, World!" with thread synchronization? 
```c
#include<stdio.h>
#include<string.h>
#include<pthread.h>
pthread_mutex_t lock;
void *create(void *arg)
{
        pthread_mutex_lock(&lock);
        printf("hello,world!\n");
        pthread_mutex_unlock(&lock);
}
int main()
{
        pthread_t t1;
        pthread_create(&t1,NULL,create,NULL);
        pthread_join(t1,NULL);
        pthread_mutex_destroy(&lock);
}
```
##
```c
