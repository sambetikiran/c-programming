## program to print HELLO WORLD
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
## Create 5 threads, each printing its own thread ID.
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
## Write a program where the main thread waits for a child thread using pthread_join().
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
}```
