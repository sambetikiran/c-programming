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
