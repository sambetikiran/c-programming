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
## 12.Develop a C program to create two threads that print their thread IDs and synchronize their output? 
```c
#include<stdio.h>
#include<pthread.h>
pthread_mutex_t lock;
void *create(void *arg)
{
        pthread_mutex_lock(&lock);
        printf("the thread of ID is%ld\n",pthread_self());
        pthread_mutex_unlock(&lock);
}
int main()
{
        pthread_t tid[2];
        for(int i=0;i<2;i++)
        {
                pthread_create(&tid[i],NULL,create,NULL);
        }
        for(int i=0;i<2;i++)
        {
                pthread_join(tid[i],NULL);
        }
}
```
## 14.Write a C program to create a thread that performs addition of two numbers with mutex locks?
```c
#include<stdio.h>
#include<pthread.h>
pthread_mutex_t lock;
void *threadfun(void *arg)
{
        pthread_mutex_lock(&lock);
        int a=10;
        int b=20;
        int add=a+b;
        printf("%d\n",add);
        pthread_mutex_unlock(&lock);
}
int main()
{
        pthread_t num;
        pthread_create(&num,NULL,threadfun,NULL);
        pthread_join(num,NULL);
}
```
## 15.Implement a C program to create two threads that increment and decrement a shared variable, respectively, using mutex locks? 
```c
#include<stdio.h>
#include<pthread.h>
#include<unistd.h>
pthread_mutex_t lock;
int num=0;
void *increment(void *arg)
{
        pthread_mutex_lock(&lock);
        num++;
        printf("%d\n",num);
        sleep(1);
        pthread_mutex_unlock(&lock);
}
void *decrement(void *arg)
{
        pthread_mutex_lock(&lock);
        num++;
        printf("%di\n",num);
        sleep(1);
        pthread_mutex_unlock(&lock);
}
int main()
{
        pthread_t inc,dec;
        pthread_create(&inc,NULL,increment,NULL);
        pthread_create(&dec,NULL,increment,NULL);
        pthread_join(inc,NULL);
        pthread_join(dec,NULL);
}
```
## 17.Implement a C program to create a thread that prints prime numbers up to a given limit with mutex locks? 
```c
#include<stdio.h>
#include<unistd.h>
#include<pthread.h>
int num[100];
int current=2;
pthread_mutex_t lock;
int isprime(int num)
{
        int flag=1;
        for(int i=2;i<num/2;i++)
        {
                if(num%i==0)
                {
                        flag=0;
                        return 0;
                }
        }
        return 1;
}
void *prime(void *arg)
{
        int lim=*(int*)arg;
        while(1)
        {
                pthread_mutex_lock(&lock);
                if(current>lim)
                {
                        pthread_mutex_unlock(&lock);
                        break;
                }
                if(isprime(current))
                {
                        printf("%d\t",current);
                }
                pthread_mutex_unlock(&lock);
                current++;
        }
}

int main()
{
        pthread_mutex_init(&lock,NULL);
        pthread_t tid;
        int limit=100;
        pthread_create(&tid,NULL,prime,&limit);
        pthread_join(tid,NULL);
}
```
## 18.Implement a C program to create a thread that calculates the sum of Fibonacci numbers up to a given limit using dynamic programming with mutex locks?
```c
#include<stdio.h>
#include<pthread.h>
pthread_mutex_t lock;
int sum=0;
int fib[100];
void *fibanocci(void *arg)
{
        int lim=*(int*)arg;
        fib[0]=0;
        fib[1]=1;
        for(int i=2;i<lim;i++)
        {
                fib[i]=fib[i-1]+fib[i-2];
        }
        for(int i=0;i<lim;i++)
        {
                pthread_mutex_lock(&lock);
                sum=sum+fib[i];
                pthread_mutex_unlock(&lock);
        }
}

int main()
{
        pthread_mutex_init(&lock,NULL);
        pthread_t fibb;
        int limit=10;
        pthread_create(&fibb,NULL,fibanocci,&limit);
        pthread_join(fibb,NULL);
        printf("%d",sum);
        pthread_mutex_destroy(&lock);
}
```
## 22.Develop a C program to create a thread that calculates the area of a triangle?
```c
#include<stdio.h>
#include<unistd.h>
#include<pthread.h>
pthread_mutex_t lock;
void *area(void *arg)
{
        int base=10;
        int height=20;
        pthread_mutex_lock(&lock);
        int area=(base*height)/2;
        printf("area of triangle is %d\n",area);
        pthread_mutex_unlock(&lock);
}
int main()
{
        pthread_t at;
        pthread_create(&at,NULL,area,NULL);
        pthread_join(at,NULL);
}
```
## 23.Write a C program to create a thread that calculates the sum of squares of numbers from 1 to 100? 
```c
#include<stdio.h>
#include<pthread.h>
pthread_mutex_t lock;
int sum=0;
void *square(void *arg)
{
        int limit=*(int*)arg;
        pthread_mutex_lock(&lock);
        for(int i=1;i<=limit;i++)
        {
                int  num=i*i;
                sum=sum+num;
        }
        pthread_mutex_unlock(&lock);
}
int main()
{
        pthread_mutex_init(&lock,NULL);
        pthread_t sq;
        int limit=100;
        pthread_create(&sq,NULL,square,&limit);
        pthread_join(sq,NULL);
        pthread_mutex_lock(&lock);
        printf("sum 0f square is %d",sum);
        pthread_mutex_unlock(&lock);
}
```
## 24.Write a C program to create a thread that generates a random array of integers?
```c
#include<stdio.h>
#include<stdlib.h>
#include<pthread.h>
#include<time.h>
#define MAX 10
int arr[MAX];
pthread_mutex_t lock;
void *array(void *arg)
{
        srand(time( NULL));
        pthread_mutex_lock(&lock);
        for(int i=0;i<MAX;i++)
        {
                arr[i]=rand()%100;
        }
        pthread_mutex_unlock(&lock);
}
int main()
{
        pthread_t ran;
        pthread_create(&ran,NULL,array,NULL);
        pthread_join(ran,NULL);
        pthread_mutex_lock(&lock);
        printf("random number\n");
        for(int i=0;i<MAX;i++)
        {
                printf("%d\t",arr[i]);
        }
        pthread_mutex_unlock(&lock);

}
```
## 26.Develop a C program to create a thread that calculates the greatest common divisor (GCD) of two numbers? 
```c
#include<stdio.h>
#include<pthread.h>
pthread_mutex_t lock;
int a=12;
int b=18;
void *divsor(void *arg)
{
        pthread_mutex_lock(&lock);
        while(b!=0)
        {
                int temp=b;
                b=a%b;
                a=temp;
        }
        pthread_mutex_unlock(&lock);
}
int main()
{
        pthread_t gcd;
        pthread_create(&gcd,NULL,divsor,NULL);
        pthread_join(gcd,NULL);
        pthread_mutex_lock(&lock);
        printf("GCD IS %d\n",a);
        pthread_mutex_unlock(&lock);
}
```
