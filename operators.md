## 1.program to find the factorial of a number
```c
#include<stdio.h>
int main()
{
        int fact,num;
        printf("enter");
        scanf("%d",&num);
        if(num<0)
        {
                printf("enter only positive numbers");
        }
        else
        {
                fact=1;
                for(int i=1;i<=num;i++)
                {
                        fact*=i;
                        printf("factorial value is %d\t",i);
                }
                printf("\n");
                printf("enter factorial is %d\n",fact);
        }
        return 0;
}
```
## 2.find the biggest number
```c
#include<stdio.h>
int main()
{
        int a,b,c;
        printf("enter the numbers");
        scanf("%d%d%d",&a,&b,&c);
        if(a>b)
        {
                if(a>c)
                        printf("a is greater than b and c");
                else
                        printf("c is greater than a and c");
        }
        else if(b>a)
        {
                if(b>c)
                        printf("b is greater than a and c");
                else
                        printf("c is greater tha b and c");
        }
}
```
## 3. program which is greater number
```c
#include<stdio.h>
int main()
{
        int a=20,b=30;
        (a>b)?printf("a is greater than b\n"):printf("b is greater than c\n");
}
```
## 4. program to print numbers in decrement
```c
#include<stdio.h>
int main()
{
        int i=10;
        while(i-->0)
                printf("%d\t",i);
}
```
## 5.program to print prime number or not
```c
#include<stdio.h>
int main()
{
        int n;
        printf("enter:");
        scanf("%d",&n);
        if(n<=0)
                printf("it is not prime number");
        else
        {
                for(int i=1;i<n;i++)
                {
                        n%i==0;
                }
                printf("%d\n",n);
        }
        return 0;
}
```
## 7.Find the maximum average of all contiguous subarrays of size 4 in a given array.
```c
#include<stdio.h>
int main()
{
        int num;
        printf("enter the number");
        scanf("%d",&num);
        int arr[num];
        for(int i=0;i<num;i++)
        {
                scanf("%d",&arr[i]);
        }
        float k=4;
        float max=0;
        float avg;
        for(int i=0;i<=num-k;i++)
        {
                int sum=0;
                int count=0;
                for(int j=i;j<i+k;j++)
                {
                        sum=sum+arr[j];
                        count++;
                }
                if(count==k)
                {
                        printf("sum=%d\n",sum);
                        avg=sum/k;
                }
                if(avg>max)
                {
                        max=avg;
                }
        }
        printf("%f",max);
}
```
## 8. print the given number is set or not
```c
#include<stdio.h>
int main()
{
        int num,i;
        printf("enter the number:");
        scanf("%d %d",&num,&i);
        if(num&(1<<i))
                printf("%d number is set",num);
        else
                printf("%d number is not set",num);
}
```
## 9.given char is alphabet or not
```c
#include<stdio.h>
void main(){
        char ch;
        printf("enter the ch value");
        scanf("%c",&ch);
        if(ch>='A'&&ch<='Z')
                printf("the given alphabet is  between AtoZ");
        else
                printf("the given alphabet is  not between AtoZ");
}
```
