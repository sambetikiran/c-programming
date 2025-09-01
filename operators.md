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
## 10.Write a C program to print numbers from 0 to 80, displaying 8 numbers per line
```c
#include<stdio.h>
int main()
{
        int  n=80;
        for(int i=0;i<=n;i++)
        {
                if(i%8==0)
                {
                        printf("\n");
                }
                printf("%d\t",i);
        }
        return 0;
}
```
## 11.Write a C program to print a pyramid of stars with a given number of rows
```c
#include<stdio.h>
int main()
{
        int num;
        printf("enter the number:");
        scanf("%d",&num);
        for(int i=1;i<num;i++)
        {
                for(int k=1;k<=num-i;k++)
                {
                        printf(" ");
                }
                for(int j=1;j<=(2*i-1);j++)
                {
                                printf(" * ");
                }
                printf("\n");
        }

}
```
## 12.write c progran to print number pattern
```c
#include<stdio.h>
int main()
{
        int num;
        printf("enter the number");
        scanf("%d",&num);
        for(int i=1;i<=num;i++)
        {
                for(int j=1;j<=i;j++)
                {
                        printf("%d\t",j);
                }
                printf("\n");
        }
        return 0;
}
```
## 13.Write a C program to find and display all Pythagorean triplets (x, y, z) where x² + y² = z² and x, y, z < 50.
```c
include<stdio.h>
int main()
{
        int x,y,z;
        for(x=1;x<50;x++)
        {
                for(y=x+1;y<50;y++)
                {
                        for(z=y+1;z<50;z++)
                        {
                                if(x*x+y*y==z*z)
                                {
                                        printf("%d**+%d**=%d**\n",x,y,z);
                                }
                        }
                }
        }
}
```
## 14 fibnacci series
```c
#include<stdio.h>
int main()
{
        int n,next,first=0,sec=1;
        printf("enter the value");
        scanf("%d",&n);
        for(int i=0;i<=n;i++)
        {
                next=first+sec;
                first=sec;
                sec=next;
                printf("%d\t",next);
        }
        printf("\n");
}
```

